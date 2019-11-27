---
title: IMetaDataAssemblyImport::GetFileProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447216"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>IMetaDataAssemblyImport::GetFileProps 메서드
지정 된 메타 데이터 시그니처를 사용 하 여 파일의 속성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mdf`  
 진행 속성을 가져올 파일을 나타내는 `mdFile` 메타 데이터 토큰입니다.  
  
 `szName`  
 제한이 파일의 단순한 이름입니다.  
  
 `cchName`  
 진행 `szName`의 크기 (와이드 문자)입니다.  
  
 `pchName`  
 제한이 `szName`에서 실제로 반환 되는 와이드 문자 수입니다.  
  
 `ppbHashValue`  
 제한이 해시 값에 대 한 포인터입니다. 이는 파일의 SHA-1 알고리즘을 사용 하는 해시입니다.  
  
 `pcbHashValue`  
 제한이 반환 된 해시 값의 와이드 문자 수입니다.  
  
 `pdwFileFlags`  
 제한이 파일에 적용 된 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. Flags 값은 하나 이상의 [Corfileflags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값의 조합입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
