# 8智慧型轉換/不可null的轉換
### view成為可null類型
	val view: View? = findViewById(R.layout.activity_shop)
	
### 智慧型轉換為不可null類型		  
	val view: View? //只可以應用在val 變數
	if ( view != null ){
	     view.isShown()     // view被轉換為不可null類型
	}
	view.isShown() //錯誤(超出範圍)

### 智慧型轉換為不可null類型
	fun main() {
	    val name:String? = "robert";
	    if (name != null){
	        println(name.length);
	    }
	}	


### 智慧型轉換可以利用return,讓function剩下範圍都有智慧型轉換
	fun setView(view: View?){
	    if (view == null)
	        return
	            
	     view.isShown() //view被轉換為不可null類型
	}
	
### 智慧型轉換可以利用return,讓function剩下範圍都有智慧型轉換
	fun main() {
	    val name:String? = "robert";
	    if (name == null) return
	    println(name.length);
	}
	
### 智慧型轉換可以利用return,讓function剩下範圍都有智慧型轉換
	fun verifyView(view: View?){
	     view ?: return
	            
	     view.isShown()  //view被轉換為不可null類型
	     //..
	}
	
### 智慧型轉換可以利用return,讓function剩下範圍都有智慧型轉換
	fun main() {
	    var name:String? = "robert";
	    name ?: return
	    println(name.length);
	}

### 智慧型轉換可以利用throw,讓function剩下範圍都有智慧型轉換
	fun setView(view: View?){
	    view ?: throw RuntimeException("View is empty")
	    
	    view.isShown() //view被轉換為不可null類型
	 }