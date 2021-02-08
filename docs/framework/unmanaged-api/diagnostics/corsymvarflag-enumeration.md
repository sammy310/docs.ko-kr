---
description: '다음에 대 한 자세한 정보: CorSymVarFlag 열거형'
title: CorSymVarFlag 열거형
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: 28f4b4775e20703e5dcaa7daf69affd3548aa3f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800463"
---
# <a name="corsymvarflag-enumeration"></a>CorSymVarFlag 열거형

변수가 컴파일러에서 생성 되었는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|지정 된 변수가 컴파일러에서 생성 되었음을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 열거형](diagnostics-symbol-store-enumerations.md)
