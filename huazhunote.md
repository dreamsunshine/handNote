启动：/etc/init.d/shadowsocks start  
停止：/etc/init.d/shadowsocks stop  
重启：/etc/init.d/shadowsocks restart  
状态：/etc/init.d/shadowsocks status

// Create a custom error  
var SpecifiedError = function SpecifiedError\(message\) {  
  this.name = 'SpecifiedError';  
  this.message = message \|\| '';  
  this.stack = \(new Error\(\)\).stack;  
};  
SpecifiedError.prototype = new Error\(\);  
SpecifiedError.prototype.constructor = SpecifiedError;  
throw new SpecifiedError

// scripts/errorAjaxHandlerDom.js  
window.addEventListener\('error', function \(e\) {  
  var stack = e.error.stack;  
  var message = e.error.toString\(\);  
  if \(stack\) {  
    message += '\n' + stack;  
  }  
  var xhr = new XMLHttpRequest\(\);  
  xhr.open\('POST', '/log', true\);  
  // Fire an Ajax request with error details  
  xhr.send\(message\);  
}\);

$\(window\).on\('scroll.elasticity',function \(e\){e.preventDefault\(\);}\).on\('touchmove.elasticity',function\(e\){e.preventDefault\(\);}\);

choco  install/upgrade packagename -ia "INSTALLDIR=""D:\Program Files""" 
choco install notepadplusplus.install -ia "'/D=E:\SomeDirectory\somebody\npp'"
--install-directory=value



