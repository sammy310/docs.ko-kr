---
title: GetALinkMessageDll 함수
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449350"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll 함수
메시지 DLL을 찾아서 로드 합니다. 메시지 DLL을 찾을 수 없거나 로드할 수 없는 경우 0을 반환 합니다. 메시지 DLL은 이름이 언어 ID 이거나 현재 디렉터리에 있는 하위 디렉터리에 있어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** alink. h  
  
 **라이브러리**: alink .dll  
  
## <a name="see-also"></a>참고 항목

- [Al.exe(어셈블리 링커)](../../tools/al-exe-assembly-linker.md)
