# Flutter Animated Tap Builder

A simple widget for building interactive areas. It is an alternative to the material's Inkwell that allows customizing the visual effects.

## Quickstart

   ```
   @override
Widget build(BuildContext context) {
    return TapBuilder(
        onTap: () {},
        builder: (context, state, isFocused) => AnimatedContainer(
            padding: EdgeInsets.symmetric(
                vertical: 10,
                horizontal: 20,
            ),
            duration: const Duration(milliseconds: 500),
            decoration: BoxDecoration(
                border: Border.all(
                    color: Colors.white.withOpacity(isFocused ? 0.2 : 0.0),
                    width: 2,
                ),
                color: () {
                    switch (state) {
                        case TapState.disabled:
                            return Colors.grey;
                        case TapState.hover:
                            return Colors.blue;
                        case TapState.inactive:
                            return Colors.amberAccent;
                        case TapState.pressed:
                            return Colors.red;
                    }
                }(),
            ),
            child: Text('Button'),
        ),
    );
}
   ```


