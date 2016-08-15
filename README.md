# annotation_tags

<pre>
@Configuration  定义该类是一个配置类
@Bean           手动声明一个Bean

@Component                              //只要定义了该注解，就会被ComponentScan发现并自动装配
@Component("指定BeanID")
@ComponentScan("com.weib.soundsystem") //指定包名   指定的包名包含子目录
@ComponentScan(basePackages={"com.weib.soundsystem"}) //指定多个包名
@ComponentScan(basePackageClasses={SgtPeppers.class, CDPlayer.class})   //指定组件类　

@Autowired

@Import(ProfileBeansConfig.class)
@Import({ProProfileConfig.class, QaProfileConfig.class, DevProfileConfig.class})

@Profile("dev")
@ActiveProfiles

@Conditional(Conditional's child object .class)	条件化的Bean

@Primary  优先装配的Bean
@Qualifier("自定义限定符")  只有在自动装配时有效

@Scope()	作用域:单例（Singleton）	原型（Prototype）	会话（Session）和请求（Request）

@PropertySource("classpath:app.properties") //要放到resources目录下
@Value("${disc.title}") String title
@Value("#{'test'}") String artist


@Aspect 声明一个POJO为切面
@Pointcut("execution(* com.weib.concert.beans.Performance.perform(..))") 定义切点
@Pointcut("execution(* com.weib.concert.beans.cd.CD.play(int)) && args(index)")	在切面中传递参数
@Before("performance()") 在切点前执行
@AfterReturning("performance()") 在切点返回后执行
@AfterThrowing("performance()") 在切点异常时执行
@Around("performance()") 代理执行切点为，通过ProceedingJoinPoint#proceed()执行切点方法的代码

@EnableAspectJAutoProxy 在Config中声明切点为自动代理

@DeclareParents(value="com.weib.concert.beans.Performance+", defaultImpl=PerformanceEncoreable.class)	//参过切面扩展接口



</pre>
