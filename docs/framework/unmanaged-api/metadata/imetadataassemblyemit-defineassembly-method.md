---
title: IMetaDataAssemblyEmit::DefineAssembly 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177897"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly 메서드
지정된 `Assembly` 어셈블리에 대한 메타데이터가 포함된 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbPublicKey`  
 【인】 어셈블리의 게시자를 식별하는 공개 키 또는 어셈블리의 이름이 지정되지 않은 경우 NULL입니다.  
  
 `cbPublicKey`  
 【인】 의 바이트 크기입니다. `pbPublicKey`  
  
 `uHashAlgId`  
 【인】 어셈블리의 파일을 암호화하는 데 사용할 해싱 알고리즘또는 NULL을 사용하여 SHA-1 알고리즘을 지정하는 데 사용할 해시 알고리즘의 식별자입니다.  
  
 `szName`  
 【인】 어셈블리의 사람이 읽을 수 있는 텍스트 이름입니다. 이 값은 1024자를 초과해서는 안 됩니다.  
  
 `pMetaData`  
 【인】 어셈블리에 대한 버전, 플랫폼 및 로캘 정보를 포함하는 ASSEMBLYMETADATA 인스턴스에 대한 포인터입니다.  
  
 `dwAssemblyFlags`  
 【인】 [어셈블리의](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 기능을 설명하는 CorAssemblyFlags 값의 조합입니다.  
  
 `pmda`  
 【아웃】 메타데이터 토큰에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 매니페스트 `Assembly` 내에서 하나의 메타데이터 구조만 정의할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
