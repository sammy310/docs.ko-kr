---
title: IMethodMalloc 인터페이스
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee825da1f3f0fd72a3b47b48783f0f344af99b65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969815"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc 인터페이스
새 Microsoft MSIL (intermediate language) 함수 본문에 대 한 메모리를 할당 하는 메서드를 제공 합니다.  
  
> [!NOTE]
>  `IMethodMalloc` 인터페이스는 간단한 메모리 할당자입니다. 메모리를 할당할 수 있지만 해제할 수는 없습니다 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Alloc 메서드](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|새 MSIL 함수 본문에 지정된 된 양의 메모리를 할당 하려고 시도 합니다.|  
  
## <a name="remarks"></a>설명  
 각 할당자는 특정 모듈 및 모듈의 기본부터 양수 오프셋에서 함수 본문 되도록 보장 합니다. 모듈의 기본 메모리 할당자를 사용 하 여 함수 본문에만 메모리를 할당 해야 하므로 귀중 한를 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
