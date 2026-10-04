## Descripcion
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/b9cfc84c442958b8ac848ddc0692bed9ef01a15877b8d37f36afbe68b5849acc/fixme1.tar.gz).
## Solucion
```

┌──(celesteh㉿K-Celeste)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/b9cfc84c442958b8ac848ddc0692bed9ef01a15877b8d37f36afbe68b5849acc/fixme1.tar.gz

2026-10-03 12:13:41 (7.18 MB/s) - ‘fixme1.tar.gz’ saved [1549/1549]


┌──(celesteh㉿K-Celeste)-[~]
└─$ tar -xvf fixme1.tar.gz
fixme1/
fixme1/Cargo.lock
fixme1/Cargo.toml
fixme1/src/
fixme1/src/main.rs

┌──(celesteh㉿K-Celeste)-[~]
└─$ cat fixme1/src/main.rs
use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS") // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["71", "35", "11", "73", "2f", "17", "53", "71", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        ret; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        ":?", // How do we print out a variable in the println function?
        String::from_utf8_lossy(&decrypted_buffer)
    );
}
┌──(celesteh㉿K-Celeste)-[~]
└─$ nano fixme1/src/main.rs

┌──(celesteh㉿K-Celeste)-[~]
└─$ cd fixme1

┌──(celesteh㉿K-Celeste)-[~/fixme1]
└─$ nano src/main.rs

┌──(celesteh㉿K-Celeste)-[~/fixme1]
└─$ cargo run
   Compiling rust_proj v0.1.0 (/home/celesteh/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.86s
     Running `target/debug/rust_proj`
academy{4r3_y0u_4_ru$t4c30n_n0w?}

┌──(celesteh㉿K-Celeste)-[~/fixme1]
└─$
```
## Notas adicionales
## Referencias