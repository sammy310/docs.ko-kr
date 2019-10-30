---
title: IInstallReferenceItem::GetReference 메서드
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
ms.openlocfilehash: 014bd4f2b12c84790065f76a67765aaf35e8b2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131674"
---
# <a name="iinstallreferenceitemgetreference-method"></a>IInstallReferenceItem::GetReference 메서드
이 [Iinstallreferenceitem](iinstallreferenceitem-interface.md) 개체가 나타내는 [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) 구조체에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppRefData`  
 제한이 반환 된 `FUSION_INSTALL_REFERENCE` 포인터입니다.  
  
 `dwFlags`  
 진행 향후 확장성을 위해 예약 되었습니다. `dwFlags` 0 이어야 합니다.  
  
 `pvReserved`  
 진행 향후 확장성을 위해 예약 되었습니다. `pvReserved`은 null 참조 여야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IInstallReferenceItem 인터페이스](iinstallreferenceitem-interface.md)
- [FUSION_INSTALL_REFERENCE 구조체](fusion-install-reference-structure.md)
