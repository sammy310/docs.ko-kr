---
description: '자세히 알아보기: IAssemblyName:: Finalize 메서드'
title: IAssemblyName::Finalize 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.Finalize
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Finalize
helpviewer_keywords:
- Finalize method [.NET Framework fusion]
- IAssemblyName::Finalize method [.NET Framework fusion]
ms.assetid: 610e792d-98ef-411f-90b0-5b9a3813f547
topic_type:
- apiref
ms.openlocfilehash: d6277fdbc15f6f907d5e758dac4a3670570d585d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760773"
---
# <a name="iassemblynamefinalize-method"></a>IAssemblyName::Finalize 메서드

소멸자가 호출 되기 전에이 [IAssemblyName](iassemblyname-interface.md) 개체가 리소스를 해제 하 고 다른 정리 작업을 수행할 수 있도록 허용 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
