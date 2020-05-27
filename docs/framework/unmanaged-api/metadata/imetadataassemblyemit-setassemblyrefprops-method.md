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
ms.openlocfilehash: fb381a872cbeb787da0c6920f2cdeef434fb33ea
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008094"
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
 진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `AssemblyRef` .  
  
 `pbPublicKeyOrToken`  
 진행 참조 된 어셈블리의 게시자에 대 한 공개 키입니다.  
  
 `cbPublicKeyOrToken`  
 진행 의 크기 (바이트) `pbPublicKeyOrToken` 입니다.  
  
 `szName`  
 진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.  
  
 `pMetaData`  
 진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.  
  
 `pbHashValue`  
 진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.  
  
 `cbHashValue`  
 진행 의 크기 (바이트) `pbHashValue` 입니다.  
  
 `dwAssemblyRefFlags`  
 진행 참조 된 어셈블리의 특성을 지정 하는 [Assemblyrefflags](assemblyrefflags-enumeration.md) 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  
 `AssemblyRef`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) 메서드를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
