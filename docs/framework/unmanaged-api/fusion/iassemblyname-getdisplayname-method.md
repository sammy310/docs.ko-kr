---
description: '자세히 알아보기: IAssemblyName:: GetDisplayName 메서드'
title: IAssemblyName::GetDisplayName 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
ms.openlocfilehash: 9b52a901385fa9b3ba7cb6bcd1678d0718f8f695
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760760"
---
# <a name="iassemblynamegetdisplayname-method"></a>IAssemblyName::GetDisplayName 메서드

이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리의 사람이 읽을 수 있는 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szDisplayName`  
 제한이 참조 된 어셈블리의 이름을 포함 하는 문자열 버퍼입니다.  
  
 `pccDisplayName`  
 [in, out] `szDisplayName` Null 종결자 문자를 포함 하는 와이드 문자 단위의 크기입니다.  
  
 `dwDisplayFlags`  
 진행 의 기능에 영향을 주는 [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) 값의 비트 조합입니다 `szDisplayName` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
- [Fusion 열거형](fusion-enumerations.md)
