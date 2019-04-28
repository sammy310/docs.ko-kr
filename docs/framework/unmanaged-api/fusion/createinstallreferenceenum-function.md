---
title: CreateInstallReferenceEnum 함수
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7820b33dcfacae5ede5235607e40d95940fc474
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771906"
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum 함수
포인터를 가져는 [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) 인스턴스는 지정된 된 어셈블리에 대 한 응용 프로그램의 참조 목록을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppRefEnum`  
 [out] 반환 된 `IInstallReferenceEnum` 포인터입니다.  
  
 `pName`  
 [in] 합니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 참조를 열거 하는 어셈블리를 식별 하는 합니다.  
  
 `dwFlags`  
 [in] 열거자의 동작에 영향을 주는 플래그입니다.  
  
 `pvReserved`  
 [in] 향후 확장성을 위해 예약 되어 있습니다. `pvReserved` null 참조 여야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다. 올바른 버전의.NET Framework 대상 지정 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IInstallReferenceEnum 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
- [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
