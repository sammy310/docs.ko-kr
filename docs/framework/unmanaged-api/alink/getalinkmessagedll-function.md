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
ms.openlocfilehash: edd83e62b08aa7892c01577cd8c46f9d965c0894
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163022"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="45309-102">GetALinkMessageDll 함수</span><span class="sxs-lookup"><span data-stu-id="45309-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="45309-103">페이지를 찾아서 메시지 DLL을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="45309-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="45309-104">메시지 DLL 찾거나 로드할 수 없습니다 경우 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="45309-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="45309-105">메시지 DLL 이름이 되는 언어 ID, 하위 디렉터리 또는 현재 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45309-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45309-106">구문</span><span class="sxs-lookup"><span data-stu-id="45309-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="45309-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45309-107">Requirements</span></span>  
 <span data-ttu-id="45309-108">**헤더:** alink.h</span><span class="sxs-lookup"><span data-stu-id="45309-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="45309-109">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="45309-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45309-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="45309-110">See also</span></span>

- [<span data-ttu-id="45309-111">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="45309-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
