# popExtension
封装了几个pop常用方法

/**
 为对象添加spring动画
 @param key - 动画的key
 @param PropertyName - 动画类型
 @param toValue - 与动画类型相对应的动画结束时的对象属性
 @param bounciness - 弹力 [0, 20] ,设置为负数表示使用默认值
 @param speed - spring动画的弹力速度 [0, 20] ,设置为负数表示使用默认值
 @param completedBlock - 动画结束
 */
- (void)pop_springAnimationForKey:(NSString *)key propertyName:(NSString *)PropertyName toValue:(id)toValue bounciness:(CGFloat)bounciness speed:(CGFloat)speed completed:(void (^)(BOOL)) completedBlock;


/**
 为对象添加减速动画
 @param key - 动画的key
 @param PropertyName - 动画类型
 @param velocity - 动画的初始速度
 @param deceleration - 减速比 [0, 1] ,默认0.998, 数值越大,减速越慢
 */
- (void)pop_decayAnimationForKey:(NSString *)key propertyName:(NSString *)PropertyName velocity:(id)velocity deceleration:(CGFloat)deceleration  completed:(void (^)(BOOL)) completedBlock;


/**
 为对象添加基础动画

 @param key - 动画的key
 @param PropertyName - 动画类型
 @param fromValue - 动画初始值
 @param toValue - 动画结束值
 @param duration - 动画时间
 @param timingFunction - 动画曲线
 @param completedBlock  - 结束
 */
- (void)pop_basicAnimationForKey:(NSString *)key propertyName:(NSString *)PropertyName fromValue:(id)fromValue toValue:(id)toValue duration:(CFTimeInterval)duration timingFunction:(CAMediaTimingFunction *)timingFunction completed:(void (^)(BOOL)) completedBlock;


/**
 为对象添加自定义动画

 @param key - 动画的key
 @param propertyReadBlock - readBlock
 @param propertyWriteBlock writeBlock
 @param threshold -
 @param fromValue - 动画初始值
 @param toValue - 动画结束值
 @param duration - 动画时间
 @param timingFunction - 动画曲线
 @param completedBlock - 结束
 */
- (void)pop_customAnimationForKey:(NSString *)key propertyRead:(void(^)(id obj,CGFloat values[]))propertyReadBlock  propertyWrite:(void(^)(id obj,const CGFloat values[]))propertyWriteBlock threshold:(CGFloat)threshold fromValue:(id)fromValue toValue:(id)toValue duration:(CFTimeInterval)duration timingFunction:(CAMediaTimingFunction *)timingFunction completed:(void (^)(BOOL)) completedBlock;
