---
layout: post
title:  "SpringMVC整合Swagger2"
date:   2016-11-12 12:44:01 +0800
categories: javaweb
tag: 框架整合
---

* content
{:toc}


>1.引用jar<code>maven配置</code>

			<dependency>
				<groupId>io.springfox</groupId>
				<artifactId>springfox-swagger2</artifactId>
				<version>2.4.0</version>
			</dependency>
			<dependency>
				<groupId>io.springfox</groupId>
				<artifactId>springfox-swagger-ui</artifactId>
				<version>2.4.0</version>
			</dependency>


>2.创建自定义配置类<code> basePackage 写action包名或者controller包名</code>
 
			import org.springframework.context.annotation.Bean;  
			import org.springframework.context.annotation.ComponentScan;  
			import org.springframework.context.annotation.Configuration;  
			import org.springframework.web.servlet.config.annotation.EnableWebMvc;  
			import org.springframework.web.servlet.config.annotation.WebMvcConfigurationSupport;  
			import springfox.documentation.builders.ApiInfoBuilder;  
			import springfox.documentation.builders.PathSelectors;  
			import springfox.documentation.builders.RequestHandlerSelectors;  
			import springfox.documentation.service.ApiInfo;  
			import springfox.documentation.spi.DocumentationType;  
			import springfox.documentation.spring.web.plugins.Docket;  
			import springfox.documentation.swagger2.annotations.EnableSwagger2;  
			/* 
			 * Restful API 访问路径: 
			 * http://IP:port/{context-path}/swagger-ui.html 
			 * eg:http://localhost:8080/runner/swagger-ui.html 
			 */  
			@EnableWebMvc  
			@EnableSwagger2  
			@ComponentScan(basePackages = {"*.controller"})  
			@Configuration  
			public class SwaggerConfig2 extends WebMvcConfigurationSupport{  
  
			@Bean  
			public Docket createRestApi() {  
					return 
						new Docket(DocumentationType.SWAGGER_2)  
						.apiInfo(apiInfo())  
						.select()  
						.apis(
						RequestHandlerSelectors
						.basePackage("*.controller")
						)  
						.paths(PathSelectors.any())  
						.build();  
			}  
  
			private ApiInfo apiInfo() {  
					return 
						new ApiInfoBuilder()  
						.title("标题")  
						.termsOfServiceUrl("http://www.jetty.cn")  
						.contact("内容简介")  
						.version("版本")  
						.build();  
			}  
}  


>3.spring-mvc.xml 配置bean&nbsp;&nbsp;<code>class的位置写自己配置类的地址</code>

			<bean class="*.SwaggerConfig2" /> 

			
>4.swagger 注解
			
			//分类
			@Api(tags = { "***" })
			
			//请求描述
			@ApiOperation(value = "***", notes = "***", 
					httpMethod = "POST",
					produces=MediaType.APPLICATION_JSON_UTF8_VALUE)
			
			//请求参数
			@ApiParam( name="***",value="***",required=true)
			
			//忽略api
			@ApiIgnore
			
>5.springmvc 中使用

				
			@ApiOperation(value = "增加活动访问量", 
						notes = "增加活动访问量", 
						httpMethod = "POST")
						
			@RequestMapping(value="/addActivityVisitNum",method = RequestMethod.POST)
			
			public BaseModelJson<Integer> addActivityVisitNum(
			
			@ApiParam( name="token",value="请求密钥",required=true) 
			@RequestParam(value="token",required=true) String token,
			
			@ApiParam( name="id",value="活动id",required=true) 
			@RequestParam(value="id",required=true) String id) {
	
			｝
			
[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
