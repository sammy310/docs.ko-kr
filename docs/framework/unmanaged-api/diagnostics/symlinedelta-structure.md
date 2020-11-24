---
title: SYMLINEDELTA 구조체
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690943"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA 구조체

편집의 결과로 이동 된 메서드에 대 한 정보를 기호 처리기에 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`mdMethod`|메서드의 메타 데이터 토큰입니다.|  
|`delta`|메서드가 이동 된 줄의 수입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym  
  
## <a name="see-also"></a>참조

- [진단 기호 저장소 구조체](diagnostics-symbol-store-structures.md)
