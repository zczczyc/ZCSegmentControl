# ZCSegmentControl
使用说明

```ruby
pod 'ZCSegmentControl'
```
```
- (ZCSegmentedControl *)segmentedControl {
    
    if (!_segmentedControl) {
        _segmentedControl = [[ZCSegmentedControl alloc] initWithSectionTitles:self.categoryListArray];
        //        _segmentedControl.autoresizingMask = UIViewAutoresizingFlexibleRightMargin | UIViewAutoresizingFlexibleWidth;
        _segmentedControl.frame = CGRectMake(0, kKD_SearchBarHeight+kHTMI_MoreStatusBarHeight + 20, kScreenWidth, 40);
        _segmentedControl.selectedSegmentIndex = 0;
        _segmentedControl.segmentEdgeInset = UIEdgeInsetsMake(0, 10, 0, 10);
        _segmentedControl.selectionStyle = HTMISegmentedControlSelectionStyleFullWidthStripe;
        _segmentedControl.selectionIndicatorLocation = HTMISegmentedControlSelectionIndicatorLocationDown;
        
        _segmentedControl.selectionIndicatorColor = [UIColor redColor];
        _segmentedControl.titleTextAttributes =@{NSForegroundColorAttributeName : [UIColor blackColor],NSFontAttributeName :[UIFont systemFontOfSize:14]};
        _segmentedControl.selectedTitleTextAttributes = @{NSForegroundColorAttributeName : [UIColor redColor],NSFontAttributeName :[UIFont systemFontOfSize:14]};
        
        _segmentedControl.selectionIndicatorHeight = 2.0;
        [_segmentedControl addTarget:self action:@selector(segmentPress:) forControlEvents:UIControlEventValueChanged];
//        _segmentedControl.backgroundColor = RGB(249, 249, 249);
    }
    return _segmentedControl;
}
```
```
/**
 *  segment点击事件
 *
 *  @param segment UISegmentedControl
 */
- (void)segmentPress:(ZCSegmentedControl *)segment {

  NSLog(@"%ld",(long)segment.selectedSegmentIndex);
}
```
