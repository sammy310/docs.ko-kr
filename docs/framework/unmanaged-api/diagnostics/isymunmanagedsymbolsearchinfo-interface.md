---
title: ISymUnmanagedSymbolSearchInfo 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610667"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a>ISymUnmanagedSymbolSearchInfo 인터페이스
검색 경로에 대 한 정보를 가져오는 메서드를 제공 합니다. `QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetHRESULT 메서드](isymunmanagedsymbolsearchinfo-gethresult-method.md)|HRESULT를 가져옵니다.|  
|[GetSearchPath 메서드](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|검색 경로를 가져옵니다.|  
|[GetSearchPathLength 메서드](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|검색 경로 길이를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
