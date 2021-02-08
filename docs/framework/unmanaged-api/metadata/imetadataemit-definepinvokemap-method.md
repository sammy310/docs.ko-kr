---
description: IMetaDataEmit::D efinePinvokeMap 메서드에 대해 자세히 알아보세요.
title: IMetaDataEmit::DefinePinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: 7b0477ca603241e773a67f335da579daa2ed3d30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784069"
---
# <a name="imetadataemitdefinepinvokemap-method"></a>IMetaDataEmit::DefinePinvokeMap 메서드

지정 된 토큰이 참조 하는 메서드에 대 한 PInvoke 시그니처의 기능을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `tk`  
 진행 대상 메서드에 대 한 토큰입니다.  
  
 `dwMappingFlags`  
 진행 PInvoke에서 매핑을 수행 하는 데 사용 되는 플래그입니다.  
  
 `szImportName`  
 진행 관리 되지 않는 DLL의 대상 내보내기 메서드 이름입니다.  
  
 `mrImportDLL`  
 진행 대상 네이티브 DLL의 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
