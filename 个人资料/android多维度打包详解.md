# android多维度打包 #

## 设置多维度信息 ##
- 设置多个维度


    	defaultConfig {
        	applicationId "com.example.myapplication"
        	minSdkVersion 21
        	targetSdkVersion 29
        	versionCode 1
        	versionName "1.0"

        	testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
        	//添加多维度信息（发布版本信息---测试、生产；项目；渠道）
        	**flavorDimensions "release","project","channel"**
    	}

- 为多个版本设置不同维度

    	productFlavors{
		//开发版
        devolpe{
            dimension "release"
			buildConfigField "String", "domain", '"https://xxx.xxx.xx/"'
        }
		//生产版
        product{
            dimension "release"
        }
		//项目区分
        aimoney{
			buildConfigField "String", "prodectName", '"xxx"'
            dimension "project"
        }
		Dbd{
			dimension "project"
		}


		//aimoney basic渠道
        aiBasic{
			buildConfigField "String", "channel", '"aaa"'
            dimension "channel"
        }
		aiHuawei{
			dimension "channel"
		}		
    	}

> 注意：维度信息有顺序之分，维度写在前面的，其版本设置信息会合并到其下级维度版本信息中去。如下：
> devolpeaimoneyaiBasic这个维度下的版本设置信息为
    	
	devolpeproductaiBasic{
		buildConfigField "String", "domain", '"https://xxx.xxx.xx/"'
		buildConfigField "String", "prodectName", '"xxx"'
		buildConfigField "String", "channel", '"aaa"'
	}


## 多维度下资源文件的区别设置 ##

    sourceSets {
        main {
            manifest.srcFile 'src/main/AndroidManifest.xml'
            java.srcDirs = ['src/main/java']
            resources.srcDirs = ['src/main/resources']
            aidl.srcDirs = ['src/main/aidl']
            renderscript.srcDirs = ['src/maom']
            res.srcDirs = ['src/main/res']
            assets.srcDirs = ['src/main/assets']
            jniLibs.srcDir 'src/main/jniLibs'
        }
	}
> 注意java文件替换需要删除主渠道中对应的Java文件，否者会报类名重复异常（无法通过编译），资源文件会替换主渠道中的内容

    


    