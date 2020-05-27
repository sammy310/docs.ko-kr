---
title: CorRegFlags 열거형
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: d8d7a43848929e49a8cb48fb957f37213ac78f2e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007353"
---
# <a name="corregflags-enumeration"></a>CorRegFlags 열거형
모듈 또는 복합 이미지를 설치할 때 등록에 사용 되는 플래그 값을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`regNoCopy`|파일이 대상에 복사 되지 않도록 지정 합니다.|  
|`regConfig`|모듈 또는 복합 구성이 구성 임을 지정 합니다.|  
|`regHasRefs`|모듈 또는 복합에 클래스 참조가 있음을 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
