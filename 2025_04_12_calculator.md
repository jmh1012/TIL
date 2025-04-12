```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const CalculatorApp());
}

class CalculatorApp extends StatelessWidget {
  const CalculatorApp({Key? key}) : super(key: key);

  // 계산기 버튼을 생성하는 간단한 헬퍼 함수
  Widget buildCalcButton(String text, Color color) {
    return Expanded(
      child: Container(
        margin: const EdgeInsets.all(1),
        child: ElevatedButton(
          style: ElevatedButton.styleFrom(
            backgroundColor: color,
            padding: const EdgeInsets.all(24),
          ),
          onPressed: () {},
          child: Text(
            text,
            style: const TextStyle(fontSize: 24, color: Colors.white),
          ),
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Calculator',
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.black,
        body: SafeArea(
          child: Column(
            children: [
              // 디스플레이 영역
              Expanded(
                flex: 1,
                child: Container(
                  alignment: Alignment.bottomRight,
                  padding: const EdgeInsets.all(20),
                  child: const Text(
                    '0',
                    style: TextStyle(
                      fontSize: 48,
                      color: Colors.white,
                    ),
                  ),
                ),
              ),
              // 버튼 영역
              Expanded(
                flex: 3,
                child: Column(
                  children: [
                    // 1행: C, +/-, %, /
                    Row(
                      children: [
                        buildCalcButton('C', Colors.grey),
                        buildCalcButton('+/-', Colors.grey),
                        buildCalcButton('%', Colors.grey),
                        buildCalcButton('/', Colors.orange),
                      ],
                    ),
                    // 2행: 7, 8, 9, x
                    Row(
                      children: [
                        buildCalcButton('7', Colors.grey.shade800),
                        buildCalcButton('8', Colors.grey.shade800),
                        buildCalcButton('9', Colors.grey.shade800),
                        buildCalcButton('x', Colors.orange),
                      ],
                    ),
                    // 3행: 4, 5, 6, -
                    Row(
                      children: [
                        buildCalcButton('4', Colors.grey.shade800),
                        buildCalcButton('5', Colors.grey.shade800),
                        buildCalcButton('6', Colors.grey.shade800),
                        buildCalcButton('-', Colors.orange),
                      ],
                    ),
                    // 4행: 1, 2, 3, +
                    Row(
                      children: [
                        buildCalcButton('1', Colors.grey.shade800),
                        buildCalcButton('2', Colors.grey.shade800),
                        buildCalcButton('3', Colors.grey.shade800),
                        buildCalcButton('+', Colors.orange),
                      ],
                    ),
                    // 5행: 0, ., =
                    Row(
                      children: [
                        // '0' 버튼은 2배 넓게 지정
                        Expanded(
                          flex: 2,
                          child: Container(
                            margin: const EdgeInsets.all(1),
                            child: ElevatedButton(
                              style: ElevatedButton.styleFrom(
                                backgroundColor: Colors.grey.shade800,
                                padding: const EdgeInsets.all(24),
                              ),
                              onPressed: () {},
                              child: const Text(
                                '0',
                                style: TextStyle(fontSize: 24, color: Colors.white),
                              ),
                            ),
                          ),
                        ),
                        buildCalcButton('.', Colors.grey.shade800),
                        buildCalcButton('=', Colors.grey),
                      ],
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```
