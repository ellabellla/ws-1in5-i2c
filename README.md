# WS 1inch5 i2c Library
A library for interfacing with a [Waveshare 1.5 Inch OLED](https://www.waveshare.com/wiki/1.5inch_OLED_Module) over i2c.

This library supports drawing images and text to the screen using the [rusttype crate](https://crates.io/crates/rusttype), [image crate](https://crates.io/crates/image), and [imageproc crate](https://crates.io/crates/imageproc). 

## Example
```rust
let font_data: &[u8] = include_bytes!("../font.ttf");
let font: Font<'static> = Font::try_from_bytes(font_data).expect("Valid font");
let scale10 = Scale::uniform(10.0);

let screen = WS1in5::new(30, 1, 27).unwrap();
screen.clear_all().unwrap();

screen.draw_centered_text(
    0,
    0,
    "Hello World",
    &scale10,
    &font,
    false
).unwrap();
```
