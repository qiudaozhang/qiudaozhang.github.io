
jdk17 的内容





```java
package com.giant.ride.req;

import io.swagger.annotations.ApiModel;
import io.swagger.annotations.ApiModelProperty;
import lombok.Data;

import java.io.Serial;
import java.io.Serializable;

@Data
@ApiModel(value = "管理员用户角色赋予的请求实体")
public class AdminAccountAddRoleReq implements Serializable {

    @Serial
    private static final long serialVersionUID = 1086270141450653154L;
    @ApiModelProperty(value = "要给定角色的用户id")
    private Long id;
    @ApiModelProperty(value = "角色的id")
    private String role;
}

```





```kotlin
package com.giant.ride.model.mongo

import com.fasterxml.jackson.databind.annotation.JsonSerialize
import com.giant.ride.common.validator.group.AddGroup
import com.giant.ride.config.OIdSerializer
import com.giant.ride.model.base.OidModel
import com.giant.ride.model.base.PureTimeModel
import com.giant.ride.model.mongo.base.MongoIdTime
import com.giant.ride.model.mongo.base.MongoTime
import io.swagger.annotations.ApiModel
import io.swagger.annotations.ApiModelProperty
import org.bson.types.ObjectId
import org.springframework.data.annotation.Id
import org.springframework.data.mongodb.core.mapping.Document
import org.springframework.data.mongodb.core.mapping.Field
import org.springframework.data.mongodb.core.mapping.FieldType
import org.springframework.data.mongodb.core.mapping.MongoId
import java.io.Serial
import java.time.LocalDateTime
import javax.validation.constraints.NotEmpty


@Document("dial_plates")
@ApiModel(value = "表盘模型")
class DialPlates : MongoIdTime() {
//    @JsonSerialize(using = OIdSerializer::class) // 展示字符串，否则是时间戳信息
//    var _id: ObjectId? = null
//    @Id
//    @ApiModelProperty(value = "主键")
//    @MongoId(targetType = FieldType.OBJECT_ID)
//    var _id:String? = null

    @ApiModelProperty(value = "主版本号")
    var p_ver: String? = null

    @ApiModelProperty(value = "平台")
    var platform: String? = null
    @ApiModelProperty(value = "中文名称")
    var name_zh: String? = null
    @ApiModelProperty(value = "英文名称")
    var name_en: String? = null
    @ApiModelProperty(value = "form")
    var form: String? = null
    @ApiModelProperty(value = "大小")
    var size: String? = null
    @ApiModelProperty(value = "分辨率")
    var resolution: String? = null
    @ApiModelProperty(value = "主版本号")
    var version: String? = null
    @ApiModelProperty(value = "图片")
    var img: String? = null
    var download_link: String? = null
    @ApiModelProperty(value = "主题名称")
    var theme: String? = null
    @ApiModelProperty(hidden = true)

    var deleted_at: LocalDateTime? = null

    companion object {
        @Serial
        private const val serialVersionUID: Long = -4053909695587487275L

    }

}
```

