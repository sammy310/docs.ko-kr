---
title: IMetaDataImport::GetUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
ms.openlocfilehash: af3de5454ce3d4a763c216de6e8efdb39407457b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729137"
---
# <a name="imetadataimportgetuserstring-method"></a>IMetaDataImport::GetUserString 메서드

지정한 메타데이터 토큰이 나타내는 리터럴 문자열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `stk`  
 진행 연결 된 문자열을 반환할 문자열 토큰입니다.  
  
 `szString`  
 제한이 요청 된 문자열의 복사본입니다.  
  
 `cchString`  
 진행 요청 된의 최대 와이드 문자 크기입니다 `szString` .  
  
 `pchString`  
 제한이 반환 된의 와이드 문자 크기입니다 `szString` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
