# Readmes /^[0-9]{1,9}([.]{1}[0-9]{0,4}){0,1}$/g 九位整数四位小数
				{ pattern: /^(0|[1-9][0-9]{0,1}|100)$/g, message: '请输入0~100整数', trigger: 'blur' }        
				{ pattern: /^(0|[1-9][0-9]{0,3})$/g, message: '请输入0~9999整数', trigger: 'blur' }        
				{ pattern: /^(\d{1,2}(\.\d{1,2})?|100)$/g, message: '请输入0~100整数或两位小数', trigger: 'blur' }                                                    
