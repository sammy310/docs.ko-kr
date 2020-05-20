---
title: ISymUnmanagedScope 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615347"
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope 인터페이스
메서드 내의 어휘 범위를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetChildren 메서드](isymunmanagedscope-getchildren-method.md)|이 범위의 자식을 가져옵니다.|  
|[GetEndOffset 메서드](isymunmanagedscope-getendoffset-method.md)|이 범위에 대 한 끝 오프셋을 가져옵니다.|  
|[GetLocalCount 메서드](isymunmanagedscope-getlocalcount-method.md)|이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.|  
|[GetLocals 메서드](isymunmanagedscope-getlocals-method.md)|이 범위 내에 정의 된 지역 변수를 가져옵니다.|  
|[GetMethod 메서드](isymunmanagedscope-getmethod-method.md)|이 범위를 포함 하는 메서드를 가져옵니다.|  
|[GetNamespaces 메서드](isymunmanagedscope-getnamespaces-method.md)|이 범위 내에서 사용 되는 네임 스페이스를 가져옵니다.|  
|[GetParent 메서드](isymunmanagedscope-getparent-method.md)|이 범위의 부모 범위를 가져옵니다.|  
|[GetStartOffset 메서드](isymunmanagedscope-getstartoffset-method.md)|이 범위의 시작 오프셋을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2 인터페이스](isymunmanagedscope2-interface.md)
