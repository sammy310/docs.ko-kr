---
title: IMetaDataAssemblyEmit::SetManifestResourceProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
ms.openlocfilehash: 74111a175b0decbc1beef7c8df5ade59d31d845b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009147"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>IMetaDataAssemblyEmit::SetManifestResourceProps 메서드
지정된 `ManifestResource` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mr`  
 진행 수정할 메타 데이터 구조를 지정 하는 토큰입니다 `ManifestResource` .  
  
 `tkImplementation`  
 진행 `File` `AssemblyRef` 리소스 공급자에 매핑되는 또는 형식의 토큰입니다.  
  
 `dwOffset`  
 진행 파일 내 리소스의 시작에 대 한 오프셋입니다.  
  
 `dwResourceFlags`  
 진행 리소스의 특성을 지정 하는 플래그 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  
 `ManifestResource`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) 메서드를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
