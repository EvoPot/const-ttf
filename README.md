# const-ttf

A TrueType parser that can work at compile time.

### Usage example :

```rust
use const_ttf::parser::Parser;
fn main() -> Result<(),()> {
    let bytes = include_bytes!("path/to/font/file.ttf");
    let mut parser = Parser::new(bytes);
    let table_directory = parser.parse().ok_or(())?;
    for table_record in table_directory.table_records {
        println!("This font supports the {} table!",table_record.table_tag);
    }
    Ok(())
}
```
