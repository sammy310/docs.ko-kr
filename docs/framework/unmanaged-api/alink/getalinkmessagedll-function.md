---
description: '자세히 알아보기: GetALinkMessageDll 함수'
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
ms.openlocfilehash: 67a294d1f21f50cee938ddeb14d1f30b4ccf911b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637874"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="d9320-103">GetALinkMessageDll 함수</span><span class="sxs-lookup"><span data-stu-id="d9320-103">GetALinkMessageDll Function</span></span>

<span data-ttu-id="d9320-104">메시지 DLL을 찾아서 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9320-104">Finds and loads the message DLL.</span></span> <span data-ttu-id="d9320-105">메시지 DLL을 찾을 수 없거나 로드할 수 없는 경우 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9320-105">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="d9320-106">메시지 DLL은 이름이 언어 ID 이거나 현재 디렉터리에 있는 하위 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9320-106">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9320-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9320-107">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d9320-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9320-108">Requirements</span></span>  

 <span data-ttu-id="d9320-109">**헤더:** alink. h</span><span class="sxs-lookup"><span data-stu-id="d9320-109">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="d9320-110">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="d9320-110">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9320-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9320-111">See also</span></span>

- [<span data-ttu-id="d9320-112">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="d9320-112">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
