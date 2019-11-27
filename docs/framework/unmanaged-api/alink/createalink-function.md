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
ms.openlocfilehash: 9165a4db7e65fb0f409a902b06d32e9c2988aa69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446550"
---
# <a name="createalink-function"></a><span data-ttu-id="1d32a-102">CreateALink 함수</span><span class="sxs-lookup"><span data-stu-id="1d32a-102">CreateALink Function</span></span>
<span data-ttu-id="1d32a-103">어셈블리 링커의 인스턴스를 만들고 지정 된 인터페이스에 대 한 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d32a-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d32a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d32a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d32a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d32a-105">Parameters</span></span>  
  
|<span data-ttu-id="1d32a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d32a-106">Parameter</span></span>|<span data-ttu-id="1d32a-107">설명</span><span class="sxs-lookup"><span data-stu-id="1d32a-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="1d32a-108">어셈블리 링커 인터페이스 중 하나의 물리적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d32a-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="1d32a-109">성공적으로 완료 되 면 `riid` 인터페이스에 대 한 포인터를 포함 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="1d32a-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d32a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d32a-110">Requirements</span></span>  
 <span data-ttu-id="1d32a-111">**라이브러리**: alink .dll</span><span class="sxs-lookup"><span data-stu-id="1d32a-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d32a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d32a-112">See also</span></span>

- [<span data-ttu-id="1d32a-113">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="1d32a-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
