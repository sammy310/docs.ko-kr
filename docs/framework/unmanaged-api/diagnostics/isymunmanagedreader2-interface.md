---
title: ISymUnmanagedReader2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: d4c5ff46d37b1292059b18920abd8042c18bbf31
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615399"
---
# <a name="isymunmanagedreader2-interface"></a>ISymUnmanagedReader2 인터페이스
기호 저장소 내의 문서, 메서드 및 변수에 대 한 액세스를 제공 하는 기호 판독기를 나타냅니다. 이 인터페이스는 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 확장 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetMethodByVersionPreRemap 메서드](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|메서드 토큰과 편집 하며 계속 하기 버전 번호가 지정 된 경우 기호 판독기 메서드를 가져옵니다.|  
|[GetMethodsInDocument 메서드](isymunmanagedreader2-getmethodsindocument-method.md)|제공 된 문서에서 줄 정보를 포함 하는 모든 메서드를 가져옵니다.|  
|[GetSymAttributePreRemap 메서드](isymunmanagedreader2-getsymattributepreremap-method.md)|이름에 따라 사용자 지정 특성을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader 인터페이스](isymunmanagedreader-interface.md)
