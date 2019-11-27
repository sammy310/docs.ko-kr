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
ms.openlocfilehash: 8da4da38d23ed65a0fdc44a0f919ee8cad2fe18e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446271"
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope 인터페이스
메서드 내의 어휘 범위를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetChildren 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|이 범위의 자식을 가져옵니다.|  
|[GetEndOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|이 범위에 대 한 끝 오프셋을 가져옵니다.|  
|[GetLocalCount 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.|  
|[GetLocals 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|이 범위 내에 정의 된 지역 변수를 가져옵니다.|  
|[GetMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|이 범위를 포함 하는 메서드를 가져옵니다.|  
|[GetNamespaces 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|이 범위 내에서 사용 되는 네임 스페이스를 가져옵니다.|  
|[GetParent 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|이 범위의 부모 범위를 가져옵니다.|  
|[GetStartOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|이 범위의 시작 오프셋을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고자료

- [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
