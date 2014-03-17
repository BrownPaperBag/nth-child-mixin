Introduction:

nth-child($an: 2n, $sibling: '*', $count: 15)
 
$an - the counting method, eg: 2n, 3n, odd - default is 2n
$an can also be a list, with the 2nd parameter being the modifier, eg: 2 for ($an+2) or -3 for ($an-3)
$sibling - the sibling element selector, eg: 'li', 'div' - default is '*'
$count - how many sibling selectors to support, eg: 10, 20 - default is 15


Example:
.selected {
	background: #000;
	color: #fff;
}
 
.even > li:first-child {
	@include nth-child(even, 'li') {
		@extend .selected;
	}
}
 
.odd > li:first-child {
	@include nth-child(odd, 'li') {
		@extend .selected;
	}
}
 
.x3n > li:first-child {
	@include nth-child(3n, 'li') {
		@extend .selected;
	}
}
 
.x3n2 > li:first-child {
	@include nth-child((3n, 2), 'li') {
		@extend .selected;
	}
}
 
.x3n-2 > li:first-child {
	@include nth-child((3n, -2), 'li') {
		@extend .selected;
	}
}
 
.x1n4 > li {
	@include nth-child((1n, 4), 'li') {
		@extend .selected;
	}
}
 
.x5 > li:first-child {
	@include nth-child(5, 'li') {
		@extend .selected;
	}
}