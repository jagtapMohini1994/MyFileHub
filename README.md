buildscript {
	ext {
		springBootVersion = '2.0.5.RELEASE'
	}
	repositories {
		mavenCentral()
	}
	dependencies {
		classpath("org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}")
	}
}

apply plugin: 'java'
apply plugin: 'eclipse'
apply plugin: 'org.springframework.boot'
apply plugin: 'io.spring.dependency-management'

group = 'com'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = 1.8

repositories {
	mavenCentral()
}


ext {
	springBootAdminVersion = '2.0.3'
}

dependencies {      
	
	compile('org.springframework.boot:spring-boot-starter-web',
	        'org.apache.tomcat.embed:tomcat-embed-jasper'
	       ,'javax.servlet:jstl','org.json:json:20090211')
	testCompile('org.springframework.boot:spring-boot-starter-test')
}

dependencyManagement {
	imports {
		mavenBom "de.codecentric:spring-boot-admin-dependencies:${springBootAdminVersion}"
	}
}
