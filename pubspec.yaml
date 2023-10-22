import 'dart:math';
import 'package:flutter/material.dart';

void main() => runApp(ColorPaletteApp());

class ColorPaletteApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: ColorPaletteScreen(),
    );
  }
}

class ColorPaletteScreen extends StatefulWidget {
  @override
  _ColorPaletteScreenState createState() => _ColorPaletteScreenState();
}

class _ColorPaletteScreenState extends State<ColorPaletteScreen> {
  final List<Color> _colorList = [
    Colors.red,
    Colors.blue,
    Colors.green,
    Colors.yellow,
    Colors.purple,
    Colors.orange,
    Colors.cyan,
    Colors.pink,
    Colors.teal,
    Colors.indigo,
  ];

  List<Color> _currentPalette = [];

  void _generatePalette() {
    List<Color> newPalette = [];
    for (int i = 0; i < 5; i++) {
      newPalette.add(_colorList[_getRandomIndex()]);
    }
    setState(() {
      _currentPalette = newPalette;
    });
  }

  int _getRandomIndex() {
    final random = Random();
    return random.nextInt(_colorList.length);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Color Palette Generator'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            RaisedButton(
              onPressed: _generatePalette,
              child: Text('Generate Palette'),
            ),
            SizedBox(height: 20),
            if (_currentPalette.isNotEmpty)
              GridView.builder(
                gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                  crossAxisCount: 5,
                ),
                itemCount: 5,
                itemBuilder: (context, index) {
                  return Container(
                    width: 50,
                    height: 50,
                    color: _currentPalette[index],
                  );
                },
              ),
          ],
        ),
      ),
    );
  }
}
