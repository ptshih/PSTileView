What is PSTileView?
---
It's a pre-defined tiling layout scroll view designed to be used similar to a UITableView.

It supports Portrait and Landscape orientations.

I built this as a hack to show my friends. Any suggestions or improvements are very welcome!

Coming soon... A fully functional demo app.

What is PSTileViewCell?
---
It's the equivalent of UITableViewCell

It implements base methods for configuring data and calculating height

*Note: You should subclass this!*

ARC
---
Fully ARC compatible now

How to use:
---
Here's an example of creating an instance of PSCollectionView

    self.tileView = [[PSTileView alloc] initWithFrame:CGRectZero];
    self.tileView.delegate = self;
    self.tileView.tileViewDelegate = self;
    self.tileView.tileViewDataSource = self;
    self.tileView.backgroundColor = [UIColor clearColor];
    self.tileView.autoresizingMask = ~UIViewAutoresizingNone;

**Configuring a Template**
    // self.template is an NSMutableArray
    [self.template addObject:@[@"A", @"A", @"B", @"C"]];
    [self.template addObject:@[@"A", @"A", @"D", @"D"]];
    [self.template addObject:@[@"E", @"E", @"F", @"F"]];
    [self.template addObject:@[@"G", @"H", @"F", @"F"]];
    [self.template addObject:@[@"I", @"J", @"K", @"L"]];
    [self.template addObject:@[@"M", @"J", @"N", @"N"]];
    [self.template addObject:@[@"O", @"P", @"P", @"Q"]];
    [self.template addObject:@[@"R", @"S", @"T", @"U"]];


**Reloading Data**
    [self.tileView reloadData];

**Delegate and DataSource**
    - (void)tileView:(PSTileView *)tileView didSelectCell:(PSTileViewCell *)cell atIndex:(NSInteger)index {
    
    }

    - (NSInteger)numberOfTilesInTileView:(PSTileView *)tileView {
        return [self.items count];
    }

    - (NSMutableArray *)templateForTileView:(PSTileView *)tileView {
        // self.template is an NSMutableArray
        return self.template;
    }

    - (PSTileViewCell *)tileView:(PSTileView *)tileView cellForItemAtIndex:(NSInteger)index {
        return nil;
    }

License
---
Copyright (c) 2012 Peter Shih (http://petershih.com)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

Questions?
---
Feel free to send me an email if you have any questions implementing PSCollectionView!
