---
title: CreateALink 함수
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
ms.openlocfilehash: 98c6ed4657dc69554a9fcca27145f65c621492f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683733"
---
# <a name="createalink-function"></a>CreateALink 함수

어셈블리 링커의 인스턴스를 만들고 지정 된 인터페이스에 대 한 포인터를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`riid`|어셈블리 링커 인터페이스 중 하나의 물리적 이름입니다.|  
|`ppInterface`|성공적으로 완료 되 면 인터페이스에 대 한 포인터를 포함 하는 위치입니다 `riid` .|  
  
## <a name="requirements"></a>요구 사항  

 **라이브러리**: alink.dll  
  
## <a name="see-also"></a>참조

- [Al.exe(어셈블리 링커)](../../tools/al-exe-assembly-linker.md)
