---
title: CorAttributeTargets 열거형
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: 5f83cb96e39b257a1d35786130cd5ed31d071de7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443875"
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets 열거형
특성을 적용하는 데 유효한 응용 프로그램 요소를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`catAssembly`|어셈블리에 특성을 적용할 수 있습니다.|  
|`catModule`|특성은 이식 가능한 실행 파일 (.dll 또는 .exe)에 적용할 수 있습니다.|  
|`catClass`|특성은 클래스에 적용할 수 있습니다.|  
|`catStruct`|특성은 구조에 적용할 수 있습니다. 즉, 값을 입력 합니다.|  
|`catEnum`|특성을 열거형에 적용할 수 있습니다.|  
|`catConstructor`|특성은 생성자에 적용할 수 있습니다.|  
|`catMethod`|메서드에 특성을 적용할 수 있습니다.|  
|`catProperty`|특성 속성에 적용할 수 있습니다.|  
|`catField`|특성 필드에 적용할 수 있습니다.|  
|`catEvent`|이벤트에 특성을 적용할 수 있습니다.|  
|`catInterface`|특성을 인터페이스에 적용할 수 있습니다.|  
|`catParameter`|특성 매개 변수에 적용할 수 있습니다.|  
|`catDelegate`|대리자에 특성을 적용할 수 있습니다.|  
|`catGenericParameter`|제네릭 매개 변수 특성을 적용할 수 있습니다.|  
|`catAll`|특성은 모든 애플리케이션 요소에 적용할 수 있습니다.|  
|`catClassMembers`|클래스의 멤버에 특성을 적용할 수 있습니다.|  
  
## <a name="remarks"></a>주의  
 `CorAttributeTargets` 열거형 값은 비트 OR 연산으로 결합 하 여 기본 조합을 가져올 수 있습니다.  
  
 `CorAttributeTargets`는 관리 <xref:System.AttributeTargets?displayProperty=nameWithType> 열거와 유사 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
