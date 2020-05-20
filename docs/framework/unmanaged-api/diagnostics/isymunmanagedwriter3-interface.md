---
title: ISymUnmanagedWriter3 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: 006045ce101884119f676e4f6324815eb21a10a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614658"
---
# <a name="isymunmanagedwriter3-interface"></a>ISymUnmanagedWriter3 인터페이스
기호 작성기를 나타내며 문서, 시퀀스 위치, 어휘 범위 및 변수를 정의 하는 메서드를 제공 합니다. 이 인터페이스는 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) 인터페이스를 확장 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Commit 메서드](isymunmanagedwriter3-commit-method.md)|지금까지 작성 된 변경 내용을 스트림에 커밋합니다.|  
|[OpenMethod2 메서드](isymunmanagedwriter3-openmethod2-method.md)|메서드를 열고 이미지의 실제 섹션 오프셋을 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
- [ISymUnmanagedWriter2 인터페이스](isymunmanagedwriter2-interface.md)
