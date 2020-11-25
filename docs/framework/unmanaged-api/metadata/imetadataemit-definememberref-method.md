---
title: IMetaDataEmit::DefineMemberRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 597ba1884351ee6d8b7eb7e0f3f01ce3ad733304
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716657"
---
# <a name="imetadataemitdefinememberref-method"></a>IMetaDataEmit::DefineMemberRef 메서드

현재 범위를 벗어난 모듈의 멤버에 대 한 참조를 정의 하 고 해당 참조 정의에 대 한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `tkImport`  
 진행 멤버가 전역이 아닌 경우 대상 멤버의 클래스 또는 인터페이스에 대 한 토큰입니다. 멤버가 전역 멤버가 면 `mdModuleRef` 해당 다른 파일에 대 한 토큰입니다.  
  
 `szName`  
 진행 대상 멤버의 이름입니다.  
  
 `pvSigBlob`  
 진행 대상 멤버의 서명입니다.  
  
 `cbSigBlob`  
 진행 의 바이트 수 `pvSigBlob` 입니다.  
  
 `pmr`  
 제한이 `mdMemberRef` 할당 된 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
