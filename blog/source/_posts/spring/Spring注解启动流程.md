---
title: spring注解启动流程
date: 2022-01-06 15:39:04
tags: Spring
categories: 源码
---

## 启动基本代码

![image-20220106153028405](/images/image-20220106153028405.png)


```java
public AnnotatedBeanDefinitionReader(BeanDefinitionRegistry registry, Environment environment) {
   Assert.notNull(registry, "BeanDefinitionRegistry must not be null");
   Assert.notNull(environment, "Environment must not be null");
   this.registry = registry;
   this.conditionEvaluator = new ConditionEvaluator(registry, environment, null);
   // 核心方法 spring定义的核心处理类注册
   AnnotationConfigUtils.registerAnnotationConfigProcessors(this.registry);
}
```

在registerAnnotationConfigProcessors中注册了四个注解配置处理器  

1. ConfigurationClassPostProcessor
2. AutowiredAnnotationBeanPostProcessor
3. CommonAnnotationBeanPostProcessor
4. PersistenceAnnotationBeanPostProcessor

![image-20220106155004260](/images/image-20220106155004260.png)

![image-20220106154912239](/images/image-20220106154912239.png)



下面是自定义**BeanFactoryPostProcessorr**

![image-20220106162028361](/images/image-20220106162028361.png)

![image-20220106163135334](/images/image-20220106163135334.png)