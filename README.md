GitTest
=======

曲家漢 i-c0112:
-------

node.js 練習1 陣列排序:

	function example()
	{
		// merge 2 "sorted" sub array
		function merge(arr1, arr2)
		{
			var index=0;
			var i=0;
			var j=0;
			var ret=[];
			while(i<arr1.length && j<arr2.length)
			{
				//console.log("ret length: "+ret.length);
				//console.log("sz1:"+arr1.length+"; sz2="+arr2.length);
				if (arr1[i] < arr2[j])
				{
					ret[index++]=arr1[i++];
				}
				else
				{
					ret[index++]=arr2[j++];
				}
			}
			//console.log("ret length: "+ret.length);
			if (i>=arr1.length)
			{
				ret=ret.concat(arr2.slice(j));
			}
			else
			{
				ret=ret.concat(arr1.slice(i));
			}
			for (var i=0; i<ret.length; ++i)
			{
				//console.log("merged: "+i+"->"+ret[i]);
			}
			//console.log("");
			return ret;
		}
		function merge_sort(arr)
		{
			if (arr.length == 1)
			{
				return arr;
			}
					
			var A = arr.slice(0, arr.length/2);
			var B = arr.slice(arr.length/2);
			A = merge_sort(A);
			//console.log("/////////////////////");
			B = merge_sort(B);
			arr = merge(A, B);
			return arr;
		}
		var arrMain = [31, 23, 55, 37, 89];
		for (var i=0; i<5; ++i)
		{
			console.log(arrMain[i]);
		}
		console.log("=================");
		arrMain = merge_sort(arrMain);
		for (var i=0; i<5; ++i)
		{
			console.log(arrMain[i]);
		}
	}
	example();
