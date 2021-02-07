---
description: IMetaDataAssemblyEmit::D efineManifestResource 메서드에 대해 자세히 알아보세요.
title: IMetaDataAssemblyEmit::DefineManifestResource 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 53994f1777cbd2e019f14c0ccae375e6424de509
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678330"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>IMetaDataAssemblyEmit::DefineManifestResource 메서드

지정된 매니페스트 리소스에 대한 메타데이터를 포함하는 `ManifestResource` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szName`  
 진행 리소스의 이름입니다.  
  
 `tkImplementation`  
 진행 `mdtFile` `mdtAssemblyRef` 리소스 공급자에 매핑되는 또는 형식의 메타 데이터 토큰입니다. NULL 값은 메타 데이터가 포함 된 파일이 리소스 공급자 임을 나타냅니다.  
  
 `dwOffset`  
 진행 파일 내 리소스의 시작에 대 한 오프셋입니다. 독립 실행형 파일의 리소스는 항상 0입니다. 리소스가 PE (이식 가능한 실행 파일) 파일에 포함 된 경우이는 cor 헤더 파일에 지정 된 위치에서 시작 하는 리소스 BLOB의 오프셋입니다.  
  
 `dwResourceFlags`  
 진행 리소스 정의에 대 한 속성 설정을 지정 하는 플래그 값의 비트 조합입니다.  
  
 `pmdmr`  
 제한이 반환 된 메타 데이터 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `ManifestResource`각 어셈블리 파일에서 구현 되는 각 리소스에 대해 하나의 메타 데이터 구조를 정의 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
