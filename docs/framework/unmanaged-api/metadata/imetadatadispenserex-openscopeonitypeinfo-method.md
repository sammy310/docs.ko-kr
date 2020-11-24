---
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: 6056a64b354f69ce39692173da01892870fba9e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682850"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a>IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드

이 메서드가 구현되지 않은 경우 이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pITI`  
 진행 범위를 열 수 있는 형식 정보를 제공 하는 [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) 인터페이스에 대 한 포인터입니다.  
  
 `dwOpenFlags`  
 진행 열기 모드 플래그입니다.  
  
 `riid`  
 진행 원하는 인터페이스입니다.  
  
 `ppIUnk`  
 제한이 반환 된 인터페이스에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
