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
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="d3b97-102">GetALinkMessageDll 함수</span><span class="sxs-lookup"><span data-stu-id="d3b97-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="d3b97-103">메시지 DLL을 찾아서 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b97-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="d3b97-104">메시지 DLL을 찾을 수 없거나 로드할 수 없는 경우 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b97-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="d3b97-105">메시지 DLL은 이름이 언어 ID 이거나 현재 디렉터리에 있는 하위 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b97-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b97-106">구문</span><span class="sxs-lookup"><span data-stu-id="d3b97-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d3b97-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3b97-107">Requirements</span></span>  
 <span data-ttu-id="d3b97-108">**헤더:** alink. h</span><span class="sxs-lookup"><span data-stu-id="d3b97-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="d3b97-109">**라이브러리**: alink .dll</span><span class="sxs-lookup"><span data-stu-id="d3b97-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b97-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3b97-110">See also</span></span>

- [<span data-ttu-id="d3b97-111">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="d3b97-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
