---
title: IMetaDataEmit::SetModuleProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: aee258c49e6726ebef990257456fd273b01b9ef0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007847"
---
# <a name="imetadataemitsetmoduleprops-method"></a>IMetaDataEmit::SetModuleProps 메서드
[IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md)에 대 한 이전 호출로 정의 된 모듈에 대 한 참조를 업데이트 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szName`  
 진행 유니코드의 모듈 이름입니다. 전체 경로 이름이 아니라 파일 이름입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
