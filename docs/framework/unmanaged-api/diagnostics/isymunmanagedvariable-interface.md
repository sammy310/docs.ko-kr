---
title: ISymUnmanagedVariable 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610173"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable 인터페이스
매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAddressField1 메서드](isymunmanagedvariable-getaddressfield1-method.md)|이 변수의 첫 번째 주소 필드를 가져옵니다. 이는 주소 유형에 따라 달라 집니다.|  
|[GetAddressField2 메서드](isymunmanagedvariable-getaddressfield2-method.md)|이 변수의 두 번째 주소 필드를 가져옵니다. 이는 주소 유형에 따라 달라 집니다.|  
|[GetAddressField3 메서드](isymunmanagedvariable-getaddressfield3-method.md)|이 변수의 세 번째 주소 필드를 가져옵니다. 이는 주소 유형에 따라 달라 집니다.|  
|[GetAddressKind 메서드](isymunmanagedvariable-getaddresskind-method.md)|이 변수의 주소 종류를 가져옵니다.|  
|[GetAttributes 메서드](isymunmanagedvariable-getattributes-method.md)|이 변수에 대 한 특성 플래그를 가져옵니다.|  
|[GetEndOffset 메서드](isymunmanagedvariable-getendoffset-method.md)|부모 내에서이 변수의 끝 오프셋을 가져옵니다.|  
|[GetName 메서드](isymunmanagedvariable-getname-method.md)|이 변수의 이름을 가져옵니다.|  
|[GetSignature 메서드](isymunmanagedvariable-getsignature-method.md)|이 변수의 시그니처를 가져옵니다.|  
|[GetStartOffset 메서드](isymunmanagedvariable-getstartoffset-method.md)|부모 내에서이 변수의 시작 오프셋을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
