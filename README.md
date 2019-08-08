## CodeSnippets

Xcode代码段

### 目标

* 统一代码风格
* 快速构建代码
* 统一OC和Swift代码

### 使用

使用[YCode](https://github.com/yangzq007/YCode)工具快速安装，可自定义参数

	//如果出现了cmdand cmdand cmdand cmdand cmdand cmdand dquote> 输出，将多条命令拆分执行即可
	git clone https://github.com/yangzq007/YCode.git && cd YCode && npm install && npm install -g && cd .. && rm -rf YCode && echo "success"
	
	ycode init
	ycode userTag <YourUserTag>

直接使用master分支（注意：FIXME和TODO当中的userTag是YCode，建议修改）

	cd ~/Library/Developer/Xcode/UserData/
	rm -rf ~/Library/Developer/Xcode/UserData/CodeSnippets
	git clone https://github.com/yangzq007/CodeSnippets.git

注：原有自定义代码段将被清空，如果想保留，可clone本仓库，将其中的文件放置到`~/Library/Developer/Xcode/UserData/CodeSnippets`目录下即可

## 代码段

| 简写 | 功能 | 类型 | 状态 |
| --- | --- | --- | --- |
| yFixMe | FIXME | 标记 | 完成 |
| yToDo | TODO | 标记 | 完成 |
| yMark | Mark | 分段 | 完成 |
| yCellFromNib | 用Xib初始化Cell | 初始化方法 | 完成 |
| yUIButton | UIButton初始化 | 初始化 | 完成 |
| yUILabel | UILabel初始化 | 初始化 | 完成 |
| yUITextField | UITextField初始化 | 初始化 | 完成 |
| yUIColor | UIColor快速初始化 | 快速初始化 | 完成 |
| yLazyUIButton | UIButton懒加载| 懒加载 | 完成 |
| yLazyUILabel | UILabel懒加载| 懒加载 | 完成 |
| yLazyUITextField | UITextField懒加载| 懒加载 | 完成 |
| yLazyUIView | UIView懒加载| 懒加载 | 完成 |
| yTableViewDataSource | UITableViewDataSource | 代码段 | 完成 |
| yTableViewDelegate | UITableViewDelegate | 代码段 | 完成 |

### 标记

yFixMe : FIXME

	Generic
	// FIXME: YCode <#FIXME#>

yToDo : TODO

	Generic
	// TODO: YCode <#TODO#>

### 分段

yMark : Mark

	Swift
	// MARK: - <#mark#>
	
	Objective-C
	#pragma mark - <#mark#>

### 初始化方法

yCellFromNib

	Swift
	class func cellFromNib() -> <#UITableViewCell#> {
	    return Bundle.main.loadNibNamed("<#UITableViewCell#>", owner: self, options: nil)?.first as! <#UITableViewCell#>;
	}
	
	Objective-C
	+ (<#UITableViewCell#> *)cellFromNib
	{
	    return [[[NSBundle mainBundle] loadNibNamed:@"<#UITableViewCell#>" owner:nil options:nil] firstObject];
	}

### 初始化

yUIButton

	Swift
	let <#button#> = UIButton(frame: CGRect(x: <#T##CGFloat#>, y: <#T##CGFloat#>, width: <#T##CGFloat#>, height: <#T##CGFloat#>));
	<#button#>.backgroundColor = UIColor(red: <#T##CGFloat#>/255, green: <#T##CGFloat#>/255, blue: <#T##CGFloat#>/255, alpha: <#T##CGFloat#>);
	<#button#>.titleLabel?.font = UIFont.systemFont(ofSize: <#T##CGFloat#>);
	<#button#>.setTitleColor(<#T##color: UIColor?##UIColor?#>, for: UIControl.State.normal);
	<#button#>.setTitleColor(<#T##color: UIColor?##UIColor?#>, for: UIControl.State.highlighted);
	<#button#>.setTitle(<#title#>, for: UIControl.State.normal);
	<#button#>.setTitle(<#title#>, for: UIControl.State.highlighted);
	<#button#>.setImage(<#T##image: UIImage?##UIImage?#>, for: UIControl.State.normal);
	<#button#>.setImage(<#T##image: UIImage?##UIImage?#>, for: UIControl.State.highlighted);
	<#button#>.addTarget(self, action: #selector(<#selector#>), for: UIControl.Event.touchUpInside);
	
	Objective-C
	UIButton *<#button#> = [[UIButton alloc] initWithFrame:CGRectMake(<#CGFloat x#>, <#CGFloat y#>, <#CGFloat width#>, <#CGFloat height#>)];
	<#button#>.backgroundColor = [UIColor colorWithRed:<#CGFloat#>/255.0f green:<#CGFloat#>/255.0f blue:<#CGFloat#>/255.0f alpha:<#CGFloat#>];
	<#button#>.titleLabel.font = [UIFont systemFontOfSize:<#(CGFloat)#>];
	[<#button#> setTitleColor:<#color#> forState:UIControlStateNormal];
	[<#button#> setTitleColor:<#color#> forState:UIControlStateHighlighted];
	[<#button#> setTitle:<#title#> forState:UIControlStateNormal];
	[<#button#> setTitle:<#title#> forState:UIControlStateHighlighted];
	[<#button#> setImage:<#image#> forState:UIControlStateNormal];
	[<#button#> setImage:<#image#> forState:UIControlStateHighlighted];
	[<#button#> addTarget:<#target#> action:@selector(<#selector#>) forControlEvents:UIControlEventTouchUpInside];

yUILabel

	Swift
	let <#label#> = UILabel(frame: CGRect(x: <#T##CGFloat#>, y: <#T##CGFloat#>, width: <#T##CGFloat#>, height: <#T##CGFloat#>));
	<#label#>.font = UIFont.systemFont(ofSize: <#size#>);
	<#label#>.textColor = <#textColor#>;
	<#label#>.textAlignment = NSTextAlignment.center;
	<#label#>.text = "<#text#>";
	
	Objective-C
	UILabel *<#label#> = [[UILabel alloc] initWithFrame:CGRectMake(<#CGFloat x#>, <#CGFloat y#>, <#CGFloat width#>, <#CGFloat height#>)];
	<#label#>.font = [UIFont systemFontOfSize:<#(CGFloat)#>];
	<#label#>.textColor = <#textColor#>;
	<#label#>.textAlignment = NSTextAlignmentCenter;
	<#label#>.text = <#text#>;

yUITextField

	Swift
	let <#textField#> = UITextField(frame: CGRect(x: <#T##CGFloat#>, y: <#T##CGFloat#>, width: <#T##CGFloat#>, height: <#T##CGFloat#>));
	<#textField#>.font = UIFont.systemFont(ofSize: <#T##CGFloat#>);
	<#textField#>.textColor = <#textColor#>;
	<#textField#>.placeholder = <#placeholder#>;
	
	Objective-C
	UITextField *<#textField#> = [[UITextField alloc] initWithFrame:CGRectMake(<#CGFloat x#>, <#CGFloat y#>, <#CGFloat width#>, <#CGFloat height#>)];
	<#textField#>.font = [UIFont systemFontOfSize:<#(CGFloat)#>];
	<#textField#>.textColor = <#textColor#>;
	<#textField#>.placeholder = <#placeholder#>;

### 快速初始化

yUIColor

	Swift
	UIColor(red: <#T##CGFloat#>/255, green: <#T##CGFloat#>/255, blue: <#T##CGFloat#>/255, alpha: <#T##CGFloat#>)
	
	Objective-C
	[UIColor colorWithRed:<#CGFloat#>/255.0f green:<#CGFloat#>/255.0f blue:<#CGFloat#>/255.0f alpha:<#CGFloat#>]

### 懒加载

yLazyUIButton

	Swift
	lazy var <#button#>: UIButton = {
        let <#button#> = UIButton(frame: CGRect(x: <#T##CGFloat#>, y: <#T##CGFloat#>, width: <#T##CGFloat#>, height: <#T##CGFloat#>));
        <#button#>.backgroundColor = UIColor(red: <#T##CGFloat#>/255, green: <#T##CGFloat#>/255, blue: <#T##CGFloat#>/255, alpha: <#T##CGFloat#>);
        <#button#>.titleLabel?.font = UIFont.systemFont(ofSize: <#T##CGFloat#>);
        <#button#>.setTitleColor(<#T##color: UIColor?##UIColor?#>, for: UIControl.State.normal);
        <#button#>.setTitleColor(<#T##color: UIColor?##UIColor?#>, for: UIControl.State.highlighted);
        <#button#>.setTitle(<#title#>, for: UIControl.State.normal);
        <#button#>.setTitle(<#title#>, for: UIControl.State.highlighted);
        <#button#>.setImage(<#T##image: UIImage?##UIImage?#>, for: UIControl.State.normal);
        <#button#>.setImage(<#T##image: UIImage?##UIImage?#>, for: UIControl.State.highlighted);
        <#button#>.addTarget(self, action: #selector(<#selector#>), for: UIControl.Event.touchUpInside);
        return <#button#>;
    }()
	
	Objective-C
	- (UIButton *)<#button#>
	{
		if (!<#button#>) {
			<#button#> = [[UIButton alloc] initWithFrame:CGRectMake(<#CGFloat x#>, <#CGFloat y#>, <#CGFloat width#>, <#CGFloat height#>)];
        	<#button#>.backgroundColor =  [UIColor colorWithRed:<#CGFloat#>/255.0f green:<#CGFloat#>/255.0f blue:<#CGFloat#>/255.0f alpha:<#CGFloat#>];
        	<#button#>.titleLabel.font = [UIFont systemFontOfSize:<#(CGFloat)#>];
        	[<#button#> setTitleColor:<#(nullable UIColor *)#> forState:UIControlStateNormal];
        	[<#button#> setTitleColor:<#(nullable UIColor *)#> forState:UIControlStateHighlighted];
        	[<#button#> setTitle:<#title#> forState:UIControlStateNormal];
        	[<#button#> setTitle:<#title#> forState:UIControlStateHighlighted];
        	[<#button#> setImage:<#image#> forState:UIControlStateNormal];
        	[<#button#> setImage:<#image#> forState:UIControlStateHighlighted];
        	[<#button#> addTarget:<#target#> action:@selector(<#selector#>) forControlEvents:<#event#>];
    	}
    	return <#button#>;
	}
	
yLazyUILabel

	Swift
	lazy var <#label#>: UILabel = {
        let <#label#> = UILabel(frame: CGRect(x: <#T##CGFloat#>, y: <#T##CGFloat#>, width: <#T##CGFloat#>, height: <#T##CGFloat#>));
        <#label#>.font = UIFont.systemFont(ofSize: <#size#>);
        <#label#>.textColor = UIColor(red: <#red#>/255, green: <#green#>/255, blue: <#blue#>/255, alpha: <#alpha#>);
        <#label#>.textAlignment = NSTextAlignment.center;
        <#label#>.text = "<#text#>";
        return <#label#>;
    }()
    
    Objective-C
    - (UILabel *)<#label#>
	{
	    if (!<#label#>) {
	        <#label#> = [[UILabel alloc] initWithFrame:CGRectMake(<#CGFloat x#>, <#CGFloat y#>, <#CGFloat width#>, <#CGFloat height#>)];
	        <#label#>.font = [UIFont systemFontOfSize:<#(CGFloat)#>];
	        <#label#>.textColor =  [UIColor colorWithRed:<#CGFloat#>/255.0f green:<#CGFloat#>/255.0f blue:<#CGFloat#>/255.0f alpha:<#CGFloat#>];
	        <#label#>.textAlignment = NSTextAlignmentCenter;
	        <#label#>.text = <#text#>;
	    }
	    return <#label#>;
	}

yLazyUITextField

	Swift
	lazy var <#textField#>: UITextField = {
        let <#textField#> = UITextField(frame: CGRect(x: <#T##CGFloat#>, y: <#T##CGFloat#>, width: <#T##CGFloat#>, height: <#T##CGFloat#>));
        <#textField#>.font = UIFont.systemFont(ofSize: <#T##CGFloat#>);
        <#textField#>.textColor = UIColor(red: <#T##CGFloat#>/255, green: <#T##CGFloat#>/255, blue: <#T##CGFloat#>/255, alpha: <#T##CGFloat#>);
        <#textField#>.placeholder = <#placeholder#>;
        return <#textField#>
    }()
    
    Objective-C
    - (UITextField *)<#textField#>
	{
	    if (!<#textField#>) {
	        <#textField#> = [[UITextField alloc] initWithFrame:CGRectMake(<#CGFloat x#>, <#CGFloat y#>, <#CGFloat width#>, <#CGFloat height#>)];
	        <#textField#>.font = [UIFont systemFontOfSize:<#(CGFloat)#>];
	        <#textField#>.textColor =  [UIColor colorWithRed:<#CGFloat#>/255.0f green:<#CGFloat#>/255.0f blue:<#CGFloat#>/255.0f alpha:<#CGFloat#>];
	        <#textField#>.placeholder = <#placeholder#>;
	    }
	    return <#textField#>;
	}

yLazyUIView

	Swift
	lazy var <#view#>: UIView = {
        let <#view#> = UIView(frame: CGRect(x: <#T##CGFloat#>, y: <#T##CGFloat#>, width: <#T##CGFloat#>, height: <#T##CGFloat#>));
        <#view#>.backgroundColor = UIColor(red: <#T##CGFloat#>/255, green: <#T##CGFloat#>/255, blue: <#T##CGFloat#>/255, alpha: <#T##CGFloat#>);
        return <#view#>;
    }()
    
    Objective-C
    - (UIView *)<#view#>
	{
	    if (!<#view#>) {
	        <#view#> = [[UIView alloc] initWithFrame:CGRectMake(<#CGFloat x#>, <#CGFloat y#>, <#CGFloat width#>, <#CGFloat height#>)];
	        <#view#>.backgroundColor =  [UIColor colorWithRed:<#CGFloat#>/255.0f green:<#CGFloat#>/255.0f blue:<#CGFloat#>/255.0f alpha:<#CGFloat#>];
	    }
	    return <#view#>;
	}

### 代码块

UITableViewDataSource

	Swift
	// MARK: - UITableViewDataSource
    
    func numberOfSections(in tableView: UITableView) -> Int {
        return <#sectionNumber#>;
    }
    
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return <#rowNumber#>;
    }
    
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cellIdentifier:String = <#cellIdentifier#>;
        var cell = tableView.dequeueReusableCell(withIdentifier: cellIdentifier);
        if cell == nil {
            cell = <#UITableViewCell#>(style: UITableViewCell.CellStyle.default, reuseIdentifier: cellIdentifier);
        }
        
        cell?.textLabel?.text = <#text#>;
        
        return cell!;
    }
	
	Objective-C
	#pragma mark - UITableViewDataSource
	
	- (NSInteger)numberOfSectionsInTableView:(UITableView *)tableView
	{
	    return <#sectionNumber#>;
	}
	
	- (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section
	{
	    return <#rowNumber#>;
	}
	
	- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    static NSString *cellIdentifier = <#CellIdentifier#>;
	    <#UITableViewCell#> *cell = [tableView dequeueReusableCellWithIdentifier:cellIdentifier];
	    if (cell == nil) {
	        cell = [[<#UITableViewCell#> alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:cellIdentifier];
	    }
	    
	    cell.textLabel.text = <#text#>;
	    
	    return cell;
	}

UITableViewDelegate

	Swift
	// MARK: - UITableViewDelegate
	
	func tableView(_ tableView: UITableView, heightForRowAt indexPath: IndexPath) -> CGFloat {
	    return <#rowHeight#>;
	}

	func tableView(_ tableView: UITableView, heightForHeaderInSection section: Int) -> CGFloat {
	    return <#headerHeight#>;
	}
	
	func tableView(_ tableView: UITableView, heightForFooterInSection section: Int) -> CGFloat {
	    return <#footerHeight#>;
	}

	func tableView(_ tableView: UITableView, viewForHeaderInSection section: Int) -> UIView? {
	    return <#headerView#>;
	}

	func tableView(_ tableView: UITableView, viewForFooterInSection section: Int) -> UIView? {
	    return <#footerView#>;
	}
	
	func tableView(_ tableView: UITableView, willDisplay cell: UITableViewCell, forRowAt indexPath: IndexPath) {
	    <#code#>
	}
	
	func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
	    <#code#>
	}

	func tableView(_ tableView: UITableView, didDeselectRowAt indexPath: IndexPath) {
	    <#code#>
	}
	
	Objective-C
	#pragma mark - UITableViewDelegate
	
	- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    return <#rowHeight#>;
	}
	
	- (CGFloat)tableView:(UITableView *)tableView heightForHeaderInSection:(NSInteger)section
	{
	    return <#headerHeight#>;
	}
	
	- (CGFloat)tableView:(UITableView *)tableView heightForFooterInSection:(NSInteger)section
	{
	    return <#footerHeight#>;
	}
	
	- (UIView *)tableView:(UITableView *)tableView viewForHeaderInSection:(NSInteger)section
	{
	    return <#headerView#>;
	}
	
	- (UIView *)tableView:(UITableView *)tableView viewForFooterInSection:(NSInteger)section
	{
	    return <#footerView#>;
	}

	- (void)tableView:(UITableView *)tableView willDisplayCell:(UITableViewCell *)cell forRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    <#code#>
	}
	
	- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    <#code#>
	}
	
	- (void)tableView:(UITableView *)tableView didDeselectRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    <#code#>
	}

## 规划

代码段生效范围检查

UIColor代码段替换

frame类型和约束类型区分