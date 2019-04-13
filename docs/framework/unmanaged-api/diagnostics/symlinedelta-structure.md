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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159486"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA 구조체
편집 결과로 이동 된 메서드에 대 한 기호 처리기에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
 **헤더:** CorSym.idl  
  
## <a name="see-also"></a>참고자료

- [진단 기호 저장소 구조체](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
