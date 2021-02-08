---
description: '자세히 알아보기: NukeDownloadedCache 함수'
title: NukeDownloadedCache 함수
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 2239473b8e6e43a539b0507c8255d40f87e72043
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800034"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="5f9e5-103">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="5f9e5-103">NukeDownloadedCache Function</span></span>

<span data-ttu-id="5f9e5-104">CLR (공용 언어 런타임) 다운로드 캐시를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-104">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f9e5-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f9e5-105">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5f9e5-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="5f9e5-106">Return Value</span></span>  

 <span data-ttu-id="5f9e5-107">이 메서드는 Winerror.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-107">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f9e5-108">설명</span><span class="sxs-lookup"><span data-stu-id="5f9e5-108">Remarks</span></span>  

 <span data-ttu-id="5f9e5-109">CLR 다운로드 캐시는 다시 사용할 수 있도록 URL에서 다운로드 되는 강력한 이름의 어셈블리를 저장 하는 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-109">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f9e5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f9e5-110">Requirements</span></span>  

 <span data-ttu-id="5f9e5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f9e5-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5f9e5-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5f9e5-113">**라이브러리:** Fusion.dll 및 Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-113">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="5f9e5-114">Mscorwks.dll 대신 Fusion.dll를 사용 하 여 올바른 버전의 .NET Framework를 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e5-114">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="5f9e5-115">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f9e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f9e5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f9e5-116">See also</span></span>

- [<span data-ttu-id="5f9e5-117">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="5f9e5-117">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="5f9e5-118">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="5f9e5-118">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="5f9e5-119">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5f9e5-119">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
