## Pyside6.6.1 Crash Example

### Steps to reproduce

1. Press `Add` Button 
2. Press `Clean` Button
3. Press `Add` Button again
4. Crash

### Environment

- OS: MacOS 13.6.4
- Python 3.10.13
- PySide6 6.2.1
- Machine: MacBook Air 

### Crash Log

```shell
2024-03-02 17:36:26.119 python[18041:3129776] *** Terminating app due to uncaught exception 'NSRangeException', reason: '*** -[__NSArrayM objectAtIndexedSubscript:]: index 0 beyond bounds for empty array'
*** First throw call stack:
(
	0   CoreFoundation                      0x00000001a0b030e4 __exceptionPreprocess + 176
	1   libobjc.A.dylib                     0x00000001a0621fd0 objc_exception_throw + 60
	2   CoreFoundation                      0x00000001a0bed9b4 -[__NSCFString characterAtIndex:].cold.1 + 0
	3   CoreFoundation                      0x00000001a0a76b28 -[__NSArrayM objectAtIndexedSubscript:] + 188
	4   libqcocoa.dylib                     0x0000000104b9a044 _ZN20QCocoaSystemTrayIcon13emitActivatedEv + 274796
	5   libqcocoa.dylib                     0x0000000104b9a0c8 _ZN20QCocoaSystemTrayIcon13emitActivatedEv + 274928
	6   libqcocoa.dylib                     0x0000000104b98688 _ZN20QCocoaSystemTrayIcon13emitActivatedEv + 268208
	7   QtWidgets                           0x00000001046511a8 _ZN9QListView16selectionChangedERK14QItemSelectionS2_ + 204
	8   QtCore                              0x00000001052a748c _ZN11QMetaObject8activateEP7QObjectPKS_iPPv + 3808
	9   QtCore                              0x000000010546de44 _ZN19QItemSelectionModel20emitSelectionChangedERK14QItemSelectionS2_ + 216
	10  QtCore                              0x000000010546da2c _ZN19QItemSelectionModel6selectERK14QItemSelection6QFlagsINS_13SelectionFlagEE + 636
	11  QtCore                              0x000000010546d70c _ZN19QItemSelectionModel6selectERK11QModelIndex6QFlagsINS_13SelectionFlagEE + 68
	12  QtCore                              0x000000010546e8cc _ZN19QItemSelectionModel15setCurrentIndexERK11QModelIndex6QFlagsINS_13SelectionFlagEE + 260
	13  QtWidgets                           0x00000001044af338 _ZNK9QComboBox5countEv + 828
	14  QtWidgets                           0x00000001044b28b4 _ZN9QComboBoxC1ER16QComboBoxPrivateP7QWidget + 2412
	15  QtCore                              0x00000001052a7224 _ZN11QMetaObject8activateEP7QObjectPKS_iPPv + 3192
	16  QtCore                              0x0000000105456944 _ZN18QAbstractItemModel13endInsertRowsEv + 200
	17  QtGui                               0x00000001097fb7a4 _ZN18QStandardItemModel11itemChangedEP13QStandardItem + 2376
	18  QtWidgets                           0x00000001044b5910 _ZN9QComboBox10insertItemEiRK5QIconRK7QStringRK8QVariant + 368
	19  QtWidgets.abi3.so                   0x0000000108ea93a8 _ZL25Sbk_QComboBoxFunc_addItemP7_objectS0_S0_ + 1032
	20  python3.10                          0x0000000102550b9c cfunction_call + 60
	21  python3.10                          0x00000001024f1f34 _PyObject_MakeTpCall + 336
	22  python3.10                          0x00000001026271c4 _PyEval_EvalFrameDefault + 155768
	23  pydevd_frame_evaluator_darwin_310_6 0x0000000103cf7500 __pyx_f_18_pydevd_frame_eval_36pydevd_frame_evaluator_darwin_310_64_get_bytecode_while_frame_eval + 4316
	24  python3.10                          0x00000001024f3548 _PyFunction_Vectorcall + 548
	25  python3.10                          0x00000001024f7d18 method_vectorcall + 388
	26  libpyside6.abi3.6.6.dylib           0x0000000103c92750 _ZN6PySide13SignalManager20callPythonMetaMethodERK11QMetaMethodPPvP7_objectb + 536
	27  libpyside6.abi3.6.6.dylib           0x0000000103c92318 _ZN6PySide13SignalManager20SignalManagerPrivate16qtMethodMetacallEP7QObjectiPPv + 760
	28  QtCore                              0x00000001052a71f4 _ZN11QMetaObject8activateEP7QObjectPKS_iPPv + 3144
	29  QtWidgets                           0x0000000104498ec8 _ZNK15QAbstractButton11isCheckableEv + 816
	30  QtWidgets                           0x0000000104498d48 _ZNK15QAbstractButton11isCheckableEv + 432
	31  QtWidgets                           0x0000000104499c48 _ZN15QAbstractButton17mouseReleaseEventEP11QMouseEvent + 172
	32  QtWidgets                           0x00000001043e58b8 _ZN7QWidget5eventEP6QEvent + 132
	33  QtWidgets                           0x0000000104546b24 _ZN11QPushButton5eventEP6QEvent + 204
	34  QtWidgets                           0x000000010439c594 _ZN19QApplicationPrivate13notify_helperEP7QObjectP6QEvent + 272
	35  QtWidgets                           0x000000010439e5c0 _ZN12QApplication6notifyEP7QObjectP6QEvent + 5072
	36  QtCore                              0x000000010525d474 _ZN16QCoreApplication15notifyInternal2EP7QObjectP6QEvent + 292
	37  QtWidgets                           0x000000010439cb34 _ZN19QApplicationPrivate14sendMouseEventEP7QWidgetP11QMouseEventS1_S1_PS1_R8QPointerIS0_Ebb + 808
	38  QtWidgets                           0x00000001043fa860 _ZNK21QWidgetRepaintManager3rhiEv + 11080
	39  QtWidgets                           0x00000001043f9a6c _ZNK21QWidgetRepaintManager3rhiEv + 7508
	40  QtWidgets                           0x000000010439c594 _ZN19QApplicationPrivate13notify_helperEP7QObjectP6QEvent + 272
	41  QtWidgets                           0x000000010439d3e8 _ZN12QApplication6notifyEP7QObjectP6QEvent + 504
	42  QtCore                              0x000000010525d474 _ZN16QCoreApplication15notifyInternal2EP7QObjectP6QEvent + 292
	43  QtGui                               0x00000001095579ec _ZN22QGuiApplicationPrivate17processMouseEventEPN29QWindowSystemInterfacePrivate10MouseEventE + 1740
	44  QtGui                               0x00000001095b3674 _ZN22QWindowSystemInterface22sendWindowSystemEventsE6QFlagsIN10QEventLoop17ProcessEventsFlagEE + 408
	45  libqcocoa.dylib                     0x0000000104b3bd74 qt_plugin_instance + 58768
	46  CoreFoundation                      0x00000001a0a8a5ac __CFRUNLOOP_IS_CALLING_OUT_TO_A_SOURCE0_PERFORM_FUNCTION__ + 28
	47  CoreFoundation                      0x00000001a0a8a540 __CFRunLoopDoSource0 + 176
	48  CoreFoundation                      0x00000001a0a8a2b0 __CFRunLoopDoSources0 + 244
	49  CoreFoundation                      0x00000001a0a88eb8 __CFRunLoopRun + 828
	50  CoreFoundation                      0x00000001a0a88428 CFRunLoopRunSpecific + 612
	51  HIToolbox                           0x00000001aa2dedf0 RunCurrentEventLoopInMode + 292
	52  HIToolbox                           0x00000001aa2dea80 ReceiveNextEventCommon + 220
	53  HIToolbox                           0x00000001aa2de984 _BlockUntilNextEventMatchingListInModeWithFilter + 76
	54  AppKit                              0x00000001a3cb081c _DPSNextEvent + 636
	55  AppKit                              0x00000001a3caf9b8 -[NSApplication(NSEvent) _nextEventMatchingEventMask:untilDate:inMode:dequeue:] + 716
	56  AppKit                              0x00000001a3ca3e1c -[NSApplication run] + 464
	57  libqcocoa.dylib                     0x0000000104b398fc qt_plugin_instance + 49432
	58  QtCore                              0x0000000105267160 _ZN10QEventLoop4execE6QFlagsINS_17ProcessEventsFlagEE + 540
	59  QtCore                              0x000000010525db00 _ZN16QCoreApplication4execEv + 112
	60  QtWidgets.abi3.so                   0x0000000108f6b2d8 _ZL25Sbk_QApplicationFunc_execP7_object + 60
	61  python3.10                          0x00000001025517cc cfunction_vectorcall_NOARGS + 96
	62  python3.10                          0x0000000102623c90 _PyEval_EvalFrameDefault + 142148
	63  pydevd_frame_evaluator_darwin_310_6 0x0000000103cf7500 __pyx_f_18_pydevd_frame_eval_36pydevd_frame_evaluator_darwin_310_64_get_bytecode_while_frame_eval + 4316
	64  python3.10                          0x00000001025ff444 _PyEval_Vector + 532
	65  python3.10                          0x00000001025f9e8c builtin_exec + 308
	66  python3.10                          0x00000001025519a0 cfunction_vectorcall_FASTCALL + 88
	67  python3.10                          0x000000010262a570 call_function + 1620
	68  python3.10                          0x0000000102602fe8 _PyEval_EvalFrameDefault + 7836
	69  pydevd_frame_evaluator_darwin_310_6 0x0000000103cf7500 __pyx_f_18_pydevd_frame_eval_36pydevd_frame_evaluator_darwin_310_64_get_bytecode_while_frame_eval + 4316
	70  python3.10                          0x00000001024f3548 _PyFunction_Vectorcall + 548
	71  python3.10                          0x0000000102629ed8 PyObject_Vectorcall.4459 + 76
	72  python3.10                          0x0000000102626a18 _PyEval_EvalFrameDefault + 153804
	73  pydevd_frame_evaluator_darwin_310_6 0x0000000103cf7500 __pyx_f_18_pydevd_frame_eval_36pydevd_frame_evaluator_darwin_310_64_get_bytecode_while_frame_eval + 4316
	74  python3.10                          0x00000001024f3548 _PyFunction_Vectorcall + 548
	75  python3.10                          0x0000000102629ed8 PyObject_Vectorcall.4459 + 76
	76  python3.10                          0x0000000102624e30 _PyEval_EvalFrameDefault + 146660
	77  python3.10                          0x00000001024f3548 _PyFunction_Vectorcall + 548
	78  python3.10                          0x000000010260966c _PyEval_EvalFrameDefault + 34080
	79  python3.10                          0x00000001024f3548 _PyFunction_Vectorcall + 548
	80  python3.10                          0x0000000102629fb0 call_function + 148
	81  python3.10                          0x0000000102602fe8 _PyEval_EvalFrameDefault + 7836
	82  python3.10                          0x00000001025ff444 _PyEval_Vector + 532
	83  python3.10                          0x0000000102678518 run_mod + 220
	84  python3.10                          0x00000001026782b8 pyrun_file + 156
	85  python3.10                          0x0000000102677d04 _PyRun_SimpleFileObject + 316
	86  python3.10                          0x000000010267766c _PyRun_AnyFileObject + 216
	87  python3.10                          0x000000010269bc14 pymain_run_file_obj + 196
	88  python3.10                          0x000000010269b4a0 pymain_run_file + 72
	89  python3.10                          0x000000010269ab40 pymain_run_python + 340
	90  python3.10                          0x000000010269a994 Py_RunMain + 40
	91  python3.10                          0x0000000102496650 main + 56
	92  dyld                                0x00000001a0653f28 start + 2236
)
libc++abi: terminating due to uncaught exception of type NSException

Process finished with exit code 134 (interrupted by signal 6:SIGABRT)
```