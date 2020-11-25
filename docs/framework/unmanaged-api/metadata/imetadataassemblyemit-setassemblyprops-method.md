---
title: IMetaDataAssemblyEmit::SetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: 3736e7279056e015b157758b1233cf6dc5aa6d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720206"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps 메서드

지정된 `Assembly` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pma`  
 진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `Assembly` .  
  
 `pbPublicKey`  
 진행 어셈블리 게시자의 공개 키에 대 한 포인터입니다.  
  
 `cbPublicKey`  
 진행 의 크기 (바이트) `pbPublicKey` 입니다.  
  
 `ulHashAlgId`  
 진행 어셈블리 파일을 해시 하는 데 사용 되는 해시 알고리즘의 식별자입니다.  
  
 `szName`  
 진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.  
  
 `pMetaData`  
 진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA에 대 한 포인터입니다.  
  
 `dwAssemblyFlags`  
 진행 어셈블리의 다양 한 특성을 지정 하는 [Assemblyflags](assemblyflags-enumeration.md) 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  

 `Assembly`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineAssembly](imetadataassemblyemit-defineassembly-method.md) 메서드를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
