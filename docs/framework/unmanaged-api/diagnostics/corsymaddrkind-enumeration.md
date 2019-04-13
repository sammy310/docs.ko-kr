---
title: CorSymAddrKind 열거형
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adef1010d08561c0a0fe38480fe0d2f519a80b49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133525"
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind 열거형
메모리 주소 유형을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Microsoft 중간 언어 (MSIL) 로컬 변수 또는 매개 변수 인덱스를 나타냅니다.|  
|`ADDR_NATIVE_RVA`|모듈에 상대 가상 주소를 나타냅니다.|  
|`ADDR_NATIVE_REGISTER`|CPU 레지스터를 나타냅니다.|  
|`ADDR_NATIVE_REGREL`|첫 번째 주소 레지스터 이며 두 번째 주소 오프셋을 나타냅니다.|  
|`ADDR_NATIVE_OFFSET`|기본 주소에서의 오프셋을 나타냅니다.|  
|`ADDR_NATIVE_REGREG`|첫 번째 주소를 레지스터의 하위 부분이 이며 두 번째 주소 높은 부분을 나타냅니다.|  
|`ADDR_NATIVE_REGSTK`|첫 번째 주소는 레지스터의 하위 부분, 두 번째 상위 부분이 이며 세 번째 오프셋을 나타냅니다.|  
|`ADDR_NATIVE_STKREG`|첫 번째 주소는 레지스터, 두 번째는 오프셋 이며 세 번째 레지스터의 많은 부분을 나타냅니다.|  
|`ADDR_BITFIELD`|첫 번째 주소 필드의 시작 이며 두 번째 주소 필드의 길이 나타냅니다.|  
|`ADDR_NATIVE_ISECTOFFSET`|첫 번째 주소 섹션 이며 두 번째 주소 오프셋을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [진단 기호 저장소 열거형](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
