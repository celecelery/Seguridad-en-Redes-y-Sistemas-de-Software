## Descripcion
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz).
## Solucion
```

┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz
--2026-10-03 13:08:41--  https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.22, 13.226.187.66, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1720 (1.7K) [application/octet-stream]
Saving to: ‘fixme2.tar.gz’

fixme2.tar.gz                 100%[==============================================>]   1.68K  --.-KB/s    in 0s

2026-10-03 13:08:43 (10.9 MB/s) - ‘fixme2.tar.gz’ saved [1720/1720]


┌──(celesteh㉿K-Celeste)-[~]
└─$ tar -xvf fixme2.tar.gz
fixme2/
fixme2/Cargo.lock
fixme2/Cargo.toml
fixme2/src/
fixme2/src/main.rs

┌──(celesteh㉿K-Celeste)-[~]
└─$ cd fixme2

┌──(celesteh㉿K-Celeste)-[~/fixme2]
└─$ cat src/main.rs
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &String){ // How do we pass values to a function that we want to change?

    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
    println!("{}", borrowed_string);
}


fn main() {
    // Encrypted flag values
    let hex_values = ["71", "35", "11", "73", "2f", "17", "53", "71", "01", "1c", "7e", "59", "63", "e1", "61", "25", "0d", "c4", "60", "f2", "12", "a0", "18", "03", "51", "03", "36", "05", "0e", "f9", "42", "5b"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
}
┌──(celesteh㉿K-Celeste)-[~/fixme2]
└─$ nano src/main.rs

┌──(celesteh㉿K-Celeste)-[~/fixme2]
└─$ cargo run
   Compiling rust_proj v0.1.0 (/home/celesteh/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 1.32s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: academy{4r3_y0u_h4v1n5_fun_y31?}


```
## Notas adicionales
## Referencias