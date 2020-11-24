---
title: IMetaDataAssemblyEmit::DefineFile 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: 1dd71dbe0ddb894cb5ed05c32e50429d27c66aa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689331"
---
# <a name="imetadataassemblyemitdefinefile-method"></a>IMetaDataAssemblyEmit::DefineFile 메서드

이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szName`  
 진행 사용할 파일의 이름입니다.  
  
 `pbHashValue`  
 진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.  
  
 `cbHashValue`  
 진행 의 크기 (바이트) `pbHashValue` 입니다.  
  
 `dwFileFlags`  
 진행 `FileFlags` 속성 설정을 지정 하는 값의 비트 조합입니다.  
  
 `pmdf`  
 제한이 반환 된 토큰에 대 한 포인터 `File` 입니다.  
  
## <a name="remarks"></a>설명  

 `File`메타 데이터를 포함 하는 파일을 제외 하 고이 어셈블리가 빌드된 시점에이 어셈블리의 일부인 각 파일에 대해 하나의 메타 데이터 구조를 정의 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
