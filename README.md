# micam
Some python code to load Micam Ultima data format.

Example usage :

```python
    root = r"D:\DATA\MICAM\VSD\Mouse63\210521_VSD1"

    inpath = "Behavior-1-1.rsh"
    DATA = get_micam_data(os.path.join(root,inpath))
    
    real_vsd_data = DATA[0]
    #or
    real_vsd_data= DATA["matrix"]
    print(real_vsd_data.shape())
    #>> First two dims are X and Y, last dimension is time. Care , datatype is uint16, not uint8 (max value is not 255 but 65535)
    
    
    analog_signals = DATA[1]
    #or
    analog_signals = DATA["analog"]
    print(analog_signals.keys())
    #>> 'AI1' : AnalogIn1, 'AI2' : AnalogIn2, 'Stim1' : Stim1, 'Stim2' : Stim2, 'FrameAcq' : Frames incremental timings
    
    
    delta0_vsd_data = DATA[2]
    #or
    delta0_vsd_data = DATA["diff_matrix"]
    
    
```
