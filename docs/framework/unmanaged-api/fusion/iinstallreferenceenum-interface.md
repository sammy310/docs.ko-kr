---
title: IInstallReferenceEnum 인터페이스
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
ms.openlocfilehash: d3f7c24b4bd373924c44dbc0490c890e7f1322bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131729"
---
# <a name="iinstallreferenceenum-interface"></a>IInstallReferenceEnum 인터페이스
전역 어셈블리 캐시에 설치 된 참조 된 어셈블리의 열거자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetNextInstallReferenceItem 메서드](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|이 `IInstallReferenceEnum`에 포함 된 다음 `IInstallReferenceItem`에 대 한 포인터를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 인터페이스](fusion-interfaces.md)
- [IInstallReferenceItem 인터페이스](iinstallreferenceitem-interface.md)
