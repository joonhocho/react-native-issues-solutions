# react-native-issues-solutions
This repo is for me to track current React Native issues and possible/best available solutions.


## Navigation 
I've tried many navigation libraries with complete migrations between them, and nothing have really worked so far.

### https://github.com/wix/react-native-navigation
 - Will soon migrate to this one from `react-navigation`
 - At this point, I am not optimistic about pure JS-based navigation solutions
 
### https://github.com/react-community/react-navigation
 - Not production ready
 - Not actively maintained
 - `replace` is not implemented
 - screen focus listeners are not implemented
   - camera stays running after navigation away to another screen
   - all views stay rendered and kept in memory causing performance and memory problems when a stack is 3 levels deep
 - modals with stack navigator requires lots of workarounds and hacking
 - per-screen transition is not ready
 - updating navigation params (nav titles / nav button status) is very expensive and slow
 - no default protection against navigating to the same route multiple times
   
### https://github.com/expo/ex-navigation
 - Kind of replace by `react-navigation`

### https://github.com/jmurzy/react-router-native
 - Abandoned
 - Router-based approach faced limits on mobile navigation
   - navigating to same screen from different routes required route duplication
   
### NavigationExperimental
 - Deprecated in favor of `react-navigation`


## List View
Performance issues
 - scroll (rendering new rows) is laggy
 - updating multiple rows are very slow
   - multiple checkboxes
Memory issues
 - cannot properly handle large data
Initial rendering problem
 - sometimes rows are not rendered until scroll


## Keyboard Avoiding ScrollView
### iOS
 - https://github.com/douglasjunior/react-native-keyboard-manager
 
### Android
 - android:windowSoftInputMode="adjustResize"

### KeyboardAvoidingScrollView
 - buggy
 - Does not handle inputs at all
   - does not scroll to focused input


