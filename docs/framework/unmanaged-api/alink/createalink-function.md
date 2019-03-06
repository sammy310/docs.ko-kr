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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11117db08d58684cc854400424d1836ec35b8c12
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498012"
---
# <a name="createalink-function"></a><span data-ttu-id="42259-102">CreateALink 함수</span><span class="sxs-lookup"><span data-stu-id="42259-102">CreateALink Function</span></span>
<span data-ttu-id="42259-103">어셈블리 링커의 인스턴스를 만들고 지정된 된 인터페이스에 대 한 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42259-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42259-104">구문</span><span class="sxs-lookup"><span data-stu-id="42259-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42259-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42259-105">Parameters</span></span>  
  
|<span data-ttu-id="42259-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42259-106">Parameter</span></span>|<span data-ttu-id="42259-107">설명</span><span class="sxs-lookup"><span data-stu-id="42259-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="42259-108">어셈블리 링커 인터페이스 중 하나의 물리적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42259-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="42259-109">성공적으로 완료에 대 한 포인터를 포함 하는 위치는 `riid` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="42259-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42259-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42259-110">Requirements</span></span>  
 <span data-ttu-id="42259-111">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="42259-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42259-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="42259-112">See also</span></span>
- [<span data-ttu-id="42259-113">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="42259-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
