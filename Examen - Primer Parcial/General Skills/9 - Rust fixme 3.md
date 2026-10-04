## Descripcion
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz).
## Solucion
```
┌──(celesteh㉿K-Celeste)-[~/fixme2]
└─$ wget https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz

2026-10-03 13:29:30 (14.2 MB/s) - ‘fixme3.tar.gz’ saved [1915/1915]

┌──(celesteh㉿K-Celeste)-[~/fixme2]
└─$ tar -xvf fixme3.tar.gz
fixme3/
fixme3/Cargo.lock
fixme3/Cargo.toml
fixme3/src/
fixme3/src/main.rs

┌──(celesteh㉿K-Celeste)-[~/fixme2]
└─$ cd fixme3

┌──(celesteh㉿K-Celeste)-[~/fixme2/fixme3]
└─$ nano src/main.rs

┌──(celesteh㉿K-Celeste)-[~/fixme2/fixme3]
└─$ cargo run
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/celesteh/fixme2/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 7.73s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: academy{n0w_y0uv3_f1x3d_1h3m_411}

```
## Notas adicionales
## Referencias