# mandelbrot-rust

An 'embarrassingly parallel algorithm' takin advantage of Rust's thread-safe design.

## Definition

The Mandelbrot
set is defined as the set of complex numbers c for which z does not fly out to infinity.

```rust
    // given a complex number c
    // loop on z to find the mandelbrot set
    fn mandelbrot(c: Complex<f64>) {
        // Complex represents complex numbers on the cartesian plane
        // re: real numbers
        // im: imaginary numbers
        let mut z: Complex<f64> = Complex {re: 0.0, im: 0.0}
        loop {
            z = z * z + c;
        }
    }
```

Note that values of c > 0.25 && < -2.0 cause z to loop towards infinity.

A complex number, c, as we defined above, has both real and imaginary values. If we take the real as the x coordinate, and the imaginary as the y coordinate (and if we color the point black if `c` is in the mandelbrot set, or a lighter color otherwise), we get the visually striking mandelbrot set diagram.

