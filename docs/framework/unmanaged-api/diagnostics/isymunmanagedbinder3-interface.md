---
description: '자세히 알아보기: ISymUnmanagedBinder3 인터페이스'
title: ISymUnmanagedBinder3 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 6d2172fb119076cea6d0f912fb3f403d36856599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689835"
---
# <a name="isymunmanagedbinder3-interface"></a>ISymUnmanagedBinder3 인터페이스

기호 바인더 인터페이스를 확장 합니다. `QueryInterface`인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다 `ISymUnmanagedBinder` .  
  
> [!IMPORTANT]
> 신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReaderFromCallback 메서드](isymunmanagedbinder3-getreaderfromcallback-method.md)|사용자가 또는를 사용 하 여를 구현 하거나 제공 하 여 `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` 메모리에서 디버그 디렉터리 정보를 가져올 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder 인터페이스](isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder2 인터페이스](isymunmanagedbinder2-interface.md)
