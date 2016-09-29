# quick3.3-gaf-for-windows
windows系统quick-cocos2d-x 3.3版本集成gaf动画库

编译环境：
  
  系统：windows8
  
  工具：vs2013


下载：

  quick3.3 "v3"版本 
  
  下载地址：https://github.com/dualface/v3quick


  gaf "release-gaf-4"版本 （版本要与quick版本匹配，release-gaf-5应该也可以） 
  
  下载地址：https://github.com/CatalystApps/Cocos2dxGAFPlayer/tree/release-gaf-4


集成步骤：

一、解压v3quick-3.zip。 

  我将解压后的文件夹名"v3quick-3"改成了"quick-3.3"
  
二、将gaf包解压后放到\quick-3.3\external文件夹。 

  我的文件夹改名成"Cocos2dxGAFPlayer"
  
三、打开\quick-3.3\quick\player\proj.win32\player.sln

  双击即可。
  
四、导入gaf的GAFPlayer和libGAFLuaBinding

  操作方法：
  
  添加libGAFLuaBinding：
  
  1.点击 文件->添加->现有项目。
  
  2.进入目录\quick-3.3\external\Cocos2dxGAFPlayer\lua_bindings\proj.win32
  
  3.点击libGAFLuaBinding.vcxproj，点击“打开”, 成功添加libGAFLuaBinding
  
  添加GAFPlayer：
  
  1.点击 文件->添加->现有项目。
  
  2.进入目录\quick-3.3\external\Cocos2dxGAFPlayer\Library
  
  3.点击GAFPlayer.vcxproj，点击“打开”, 成功添加GAFPlayer
  
五、为player添加gaf引用

  操作方法：
  
  1.右键player3->点击"属性"，从而打开"player3"项目的属性面板。
  
  2.点击"通用属性"->"引用"->"添加新引用"。
  
  3.在"libGAFLuaBinding"前面的方块上点击，打勾表示选中。
  
  4.点击"确定"。
  
 六、代码用引入gaf。
 
  操作方法：
  
  1.找到lua_module_register.h 打开。
  
  2.#include "Cocos2dxGAFPlayer/lua_bindings/bindings/lua_gaf_main.hpp"
  
  3.在函数lua_module_register中加入append_gaf_scripts(L);
 
 七、生成解决方案，完成即可。
 
 
