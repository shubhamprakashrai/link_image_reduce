# Flutter PhotoFrame Widget

This project demonstrates the usage of a custom `PhotoFrame` widget to display images with caching and various customization options in a Flutter application. The main focus is on reducing the size of cached images to optimize storage and performance.

## Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
- [PhotoFrame Widget](#photoframe-widget)
- [Customization Options](#customization-options)
- [Dependencies](#dependencies)

## Overview

The `PhotoFrame` widget in this project leverages the `cached_network_image` and `flutter_cache_manager` packages to display images from the network with caching capabilities. The widget focuses on reducing the size of cached images to optimize storage and performance.

## Getting Started

1. Install dependencies:
    ```sh
    flutter pub add link_image_reduce
    ```
2. Run the application:
    ```sh
    flutter run
    ```

## PhotoFrame Widget

- The `PhotoFrame` widget is a reusable component designed to display network images with optional caching and customization. It focuses on reducing the image size for caching purposes.

### Example Usage

```dart
import 'package:flutter/material.dart';
import 'photo_frame.dart'; // Ensure the correct import path

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter PhotoFrame Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Flutter PhotoFrame Demo Home Page'),
    );
  }
}

class MyHomePage extends StatelessWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(title),
      ),
      body: const Center(
        child: PhotoFrame(
          imageUrl: 'https://images.unsplash.com/photo-1715698576283-d6ee92b7157a?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHx8',
          useCache: true,
          maxHeightDiskCache: 100,
          maxWidthDiskCache: 100,
          memCacheHeight: 50,
          memCacheWidth: 50,
          borderRadius: 5.0,
          placeholderColor: Colors.grey,
          errorIconColor: Colors.red,
          backgroundColorCircularProgress: Colors.black26,
          alwaysStoppedAnimationColor: Colors.purple,
          heightOfImg: 300,
          widthOfImg: 300,
        ),
      ),
    );
  }
}

```


## Customization Options
- The PhotoFrame widget offers a variety of properties to customize its behavior and appearance. Key properties for optimizing image size include:

    - imageUrl (required): The URL of the image to display.
    -  useCache (default: true): Whether to use caching for the image.
    - cacheManager: Custom cache manager configuration.
    -  maxHeightDiskCache (default: 100): Maximum height of the disk cache in pixels.
    - maxWidthDiskCache (default: 100): Maximum width of the disk cache in pixels.
    - memCacheHeight (default: 100): Height of the in-memory cache in pixels.
    - memCacheWidth (default: 100): Width of the in-memory cache in pixels.
    - borderRadius (default: 10.0): Border radius for the image corners.
    - placeholderColor: Color of the placeholder while the image is loading.
    - errorIconColor: Color of the error icon if the image fails to load.
    - backgroundColorCircularProgress: Background color of the circular progress indicator.
    - alwaysStoppedAnimationColor: Color of the circular progress indicator.
    - heightOfSizedBox: Height of the SizedBox containing the image.
    - widthOfSizedBox: Width of the SizedBox containing the image.
    - heightOfImg: Height of the displayed image.
    - widthOfImg: Width of the displayed image.
    - heightOfImgProgrss (default: 15): Height of the CircularProgressIndicator.
    - widthOfImgProgrss (default: 15): Width of the CircularProgressIndicator.
    - strokeWidthofCircular (default: 1.6): Stroke width of the CircularProgressIndicator.

# Dependencies
- Ensure you have the following dependencies in your pubspec.yaml file:

```yaml
dependencies:
  flutter:
    sdk: flutter
  cached_network_image: ^3.1.0
  flutter_cache_manager: ^3.3.0
```

# Conclusion
- This project provides a simple and customizable way to display network images in your Flutter application, with a focus on reducing the size of cached images to optimize storage and performance. Feel free to explore and modify the PhotoFrame widget to suit your needs.# link_image_reduce
