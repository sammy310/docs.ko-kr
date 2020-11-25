---
title: ISymENCUnmanagedMethod 인터페이스
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: acb8d48ed6314756e2c1a10fff314a303799fb24
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707284"
---
# <a name="isymencunmanagedmethod-interface"></a>ISymENCUnmanagedMethod 인터페이스

편집 하며 계속 하기 기능에 대 한 정보를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetDocumentsForMethod 메서드](isymencunmanagedmethod-getdocumentsformethod-method.md)|이 메서드에 줄이 있는 문서를 가져옵니다.|  
|[GetDocumentsForMethodCount 메서드](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|이 메서드에 줄이 있는 문서 수를 가져옵니다.|  
|[GetFileNameFromOffset 메서드](isymencunmanagedmethod-getfilenamefromoffset-method.md)|오프셋과 연결 된 줄의 파일 이름을 가져옵니다.|  
|[GetLineFromOffset 메서드](isymencunmanagedmethod-getlinefromoffset-method.md)|오프셋과 연결 된 줄 정보를 가져옵니다.|  
|[GetSourceExtentInDocument 메서드](isymencunmanagedmethod-getsourceextentindocument-method.md)|특정 문서에서 메서드의 가장 작은 시작 줄과 가장 큰 끝 줄을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
