```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: FirstPage(),
    );
  }
}

class FirstPage extends StatefulWidget {
  @override
  _FirstPageState createState() => _FirstPageState();
}

class _FirstPageState extends State<FirstPage> {
  @override
  void initState() {
    super.initState();
    print("FirstPage initState() called");
  }

  @override
  void dispose() {
    print("FirstPage dispose() called");
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    print("FirstPage build() called");
    return Scaffold(
      appBar: AppBar(title: Text("First Page")),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // push() 호출
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => SecondPage()),
            );
          },
          child: Text("Go to Second Page"),
        ),
      ),
    );
  }
}

class SecondPage extends StatefulWidget {
  @override
  _SecondPageState createState() => _SecondPageState();
}

class _SecondPageState extends State<SecondPage> {
  @override
  void initState() {
    super.initState();
    print("SecondPage initState() called");
  }

  @override
  void dispose() {
    print("SecondPage dispose() called");
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    print("SecondPage build() called");
    return Scaffold(
      appBar: AppBar(title: Text("Second Page")),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // pop() 호출
            Navigator.pop(context);
          },
          child: Text("Go back to First Page"),
        ),
      ),
    );
  }
}
```
