---
description: '자세히 알아보기: Init 메서드'
title: Init 메서드
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 531e05a09cbecbfb67c8c004d1e4ba1deb7e59a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662561"
---
# <a name="init-method"></a>Init 메서드

사용할 [Ialink 인터페이스](ialink-interface.md) 를 구현 하는 개체를 준비 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `pDispenser`  
 메타 데이터 디스펜서에 대 한 [IMetaDataDispenserEx 인터페이스](../metadata/imetadatadispenserex-interface.md) 포인터입니다.  
  
 `pErrorHandler`  
 선택적 오류 처리 인터페이스에 대 한 [IMetaDataError 인터페이스](../metadata/imetadataerror-interface.md) 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink 필요  
  
## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
