---
title: IMetaDataAssemblyEmit::DefineAssemblyRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: c88b7a401a19b1bd0e02edab7ef7bbee1372199e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432086"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef 메서드
이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `AssemblyRef` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbPublicKeyOrToken`  
 진행 참조 된 어셈블리의 게시자에 대 한 공개 키입니다. 도우미 함수 [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) 를 사용 하 여이 매개 변수로 전달할 공개 키의 해시를 가져올 수 있습니다.  
  
 `cbPublicKeyOrToken`  
 진행 `pbPublicKeyOrToken`의 크기 (바이트)입니다.  
  
 `szName`  
 진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다. 이 값은 1024 자를 초과할 수 없습니다.  
  
 `pMetaData`  
 진행 참조 된 어셈블리의 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스입니다.  
  
 `pbHashValue`  
 진행 참조 된 어셈블리와 연결 된 해시 데이터입니다. (선택 사항)  
  
 `cbHashValue`  
 진행 `pbHashValue`의 크기 (바이트)입니다.  
  
 `dwAssemblyRefFlags`  
 진행 실행 엔진의 동작에 영향을 주는 [Corassemblyflags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 값의 비트 조합입니다.  
  
 `pmdar`  
 제한이 반환 된 `AssemblyRef` 메타 데이터 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 어셈블리가 참조 하는 각 어셈블리에 대해 하나의 `AssemblyRef` 메타 데이터 구조를 정의 해야 합니다.  
  
 런타임에 참조 된 어셈블리의 세부 정보는 "빌드" 정보를 나타내는 것으로 어셈블리 확인자에 전달 됩니다. 그런 다음 어셈블리 확인자는 정책을 적용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
