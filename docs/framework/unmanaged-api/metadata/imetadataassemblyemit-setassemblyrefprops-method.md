---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176047"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드
지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,
    [in] const ASSEMBLYMETADATA     *pMetaData,
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ar`  
 【인】 수정할 `AssemblyRef` 메타데이터 구조를 지정하는 메타데이터 토큰입니다.  
  
 `pbPublicKeyOrToken`  
 【인】 참조된 어셈블리의 게시자의 공개 키입니다.  
  
 `cbPublicKeyOrToken`  
 【인】 의 바이트 크기입니다. `pbPublicKeyOrToken`  
  
 `szName`  
 【인】 어셈블리의 사람이 읽을 수 있는 텍스트 이름입니다.  
  
 `pMetaData`  
 【인】 어셈블리에 대한 버전, 플랫폼 및 로캘 정보를 포함하는 ASSEMBLYMETADATA 인스턴스에 대한 포인터입니다.  
  
 `pbHashValue`  
 【인】 어셈블리와 연결된 해시 데이터에 대한 포인터입니다.  
  
 `cbHashValue`  
 【인】 의 바이트 크기입니다. `pbHashValue`  
  
 `dwAssemblyRefFlags`  
 【인】 참조된 어셈블리의 특성을 지정하는 [어셈블리 RefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  
 `AssemblyRef` 메타데이터 구조를 만들려면 [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) 메서드를 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
