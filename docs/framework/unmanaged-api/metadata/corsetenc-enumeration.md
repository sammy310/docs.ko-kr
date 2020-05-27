---
title: CorSetENC 열거형
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: 93a194ea72ab894544927cf96304397b7211b5ac
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009160"
---
# <a name="corsetenc-enumeration"></a>CorSetENC 열거형
메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MDSetENCOn`|더 이상 사용되지 않습니다.|  
|`MDSetENCOff`|더 이상 사용되지 않습니다.|  
|`MDUpdateENC`|메타 데이터를 업데이트할 수 있지만 토큰을 이동할 수 없음을 나타냅니다.|  
|`MDUpdateFull`|업데이트 중에 토큰을 이동할 수 있음을 나타냅니다.|  
|`MDUpdateExtension`|업데이트는 추가로만 구성 될 수 있음을 나타냅니다. 토큰은 이동할 수 없습니다.|  
|`MDUpdateIncremental`|컴파일이 증분 임을 나타냅니다.|  
|`MDUpdateDelta`|변경 된 메타 데이터만 저장 하도록 지정 합니다.|  
|`MDUpdateMask`|`MDUpdateENC`에는, 및가 포함 됩니다 `MDUpdateFull` `MDUpdateIncremental` .|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
