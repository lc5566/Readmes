# Readmes

/** * 获取base64编码 * @param {Object} url */


	var getBase64 = function(url, option) {
		// 兼容以“file:”开头的情况
		if(0 != url.toString().indexOf("file://")) {
			url = "file://" + url;
		}
		var img = new Image();
		img.src = url; // 传过来的图片路径在这里用。
		img.onload = function() {
			var that = this;
			//生成比例 
			var w = that.width,
				h = that.height,
				scale = w / h;
			//480  你想压缩到多大，改这里
			w = 480 || w;
			h = w / scale;
			//生成canvas
			var canvas = document.createElement('canvas');
			var ctx = canvas.getContext('2d');
			canvas.setAttribute("width", w);

			canvas.setAttribute("height", h);

			ctx.drawImage(that, 0, 0, w, h);

			var base64 = canvas.toDataURL('image/jpeg', 1 || 0.8); //1最清晰，越低越模糊。

			var now = mui.now();

			if(option.dataready) {
				option.dataready(base64, now);
			}

			var temp = base64.split(',');

			if(temp.length > 1) {
				upload(temp[1], option, now);
			} else {
				var msg = 'base64转换出错';
				//option.failure(msg)
			}
		}
	};
