# Flutter POS Printer 

A library to discover printers, and send printer commands.

Support ESC/POS, TSPL Commands

## Example

### Print ESC/POS
```dart
String printerIP = '192.168.1.22';
Future printLabel(String host, Uint8List bytes) async {
  TcpPrinterConnector connector = TcpPrinterConnector(printerIP);
  TsplPrinter printer = EscPosPrinter(
    connector,
    width: 80,
  );
  await printer.image(bytes);
  printer.beep();
}
```

### Print TSPL (Label)
```dart
String printerIP = '192.168.1.23';
Future printLabel(String host, Uint8List bytes) async {
  TcpPrinterConnector connector = TcpPrinterConnector(printerIP);
  TsplPrinter printer = TsplPrinter(
    connector,
    dpi: "200",
    sizeHeight: "25",
    sizeWidth: "40",
  );
  await printer.image(bytes);
  printer.beep();
}
```

## 
## Forked from
- https://github.com/feedmepos/flutter_printer
