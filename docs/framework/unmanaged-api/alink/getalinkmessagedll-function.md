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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 323e53c45a26d5703548ebe9863978f6d3929f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787465"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="20287-102">GetALinkMessageDll 함수</span><span class="sxs-lookup"><span data-stu-id="20287-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="20287-103">메시지 DLL을 찾아서 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="20287-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="20287-104">메시지 DLL을 찾을 수 없거나 로드할 수 없는 경우 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20287-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="20287-105">메시지 DLL은 이름이 언어 ID 이거나 현재 디렉터리에 있는 하위 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20287-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20287-106">구문</span><span class="sxs-lookup"><span data-stu-id="20287-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="20287-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20287-107">Requirements</span></span>  
 <span data-ttu-id="20287-108">**헤더:** alink. h</span><span class="sxs-lookup"><span data-stu-id="20287-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="20287-109">**라이브러리**: alink .dll</span><span class="sxs-lookup"><span data-stu-id="20287-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20287-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="20287-110">See also</span></span>

- [<span data-ttu-id="20287-111">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="20287-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
