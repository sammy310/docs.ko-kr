---
title: IMetaDataDispenserEx::GetCORSystemDirectory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: ea0e6f96028afc201f498119976eb87aa762a6eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681693"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a>IMetaDataDispenserEx::GetCORSystemDirectory 메서드

현재 CLR (공용 언어 런타임)을 보유 하 고 있는 디렉터리를 가져옵니다. 이 메서드는 in-process 디버거가 사용할 때만 지원 됩니다. 다른 구성 요소에서 호출 되는 경우 E_NOTIMPL 반환 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szBuffer`  
 제한이 디렉터리 이름을 받을 버퍼입니다.  
  
 `cchBuffer`  
 진행 의 크기 (바이트)입니다 `szBuffer` .  
  
 `pchBuffer`  
 제한이 에서 실제로 반환 된 바이트 수입니다 `szBuffer` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
