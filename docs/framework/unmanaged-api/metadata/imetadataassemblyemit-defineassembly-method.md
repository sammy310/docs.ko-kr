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
ms.openlocfilehash: 17c91200730431c4c6e230b8c1561ce7c4863868
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008185"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly 메서드
지정 된 `Assembly` 어셈블리에 대 한 메타 데이터를 포함 하는 구조체를 만들고 연결 된 메타 데이터 토큰을 반환 합니다.  
  
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
 진행 어셈블리의 게시자를 식별 하는 공개 키 이거나, 어셈블리에 강력한 이름이 지정 되지 않은 경우 NULL입니다.  
  
 `cbPublicKey`  
 진행 의 크기 (바이트) `pbPublicKey` 입니다.  
  
 `uHashAlgId`  
 진행 어셈블리의 파일을 암호화 하는 데 사용할 해시 알고리즘의 식별자 이거나, SHA-1 알고리즘을 지정 하려면 NULL입니다.  
  
 `szName`  
 진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다. 이 값은 1024 자를 초과할 수 없습니다.  
  
 `pMetaData`  
 진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.  
  
 `dwAssemblyFlags`  
 진행 어셈블리의 기능을 설명 하는 [Corassemblyflags](corassemblyflags-enumeration.md) 값의 조합입니다.  
  
 `pmda`  
 제한이 메타 데이터 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `Assembly`매니페스트 내에서 메타 데이터 구조를 하나만 정의할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
