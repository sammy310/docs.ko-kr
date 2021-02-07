---
description: '자세한 정보: CreateAssemblyCache 함수'
title: CreateAssemblyCache 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 1646e1d33401c557b13ae5c025f53aef48042004
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761163"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="a4382-103">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="a4382-103">CreateAssemblyCache Function</span></span>

<span data-ttu-id="a4382-104">전역 어셈블리 캐시를 나타내는 새 [Iassemblycache](iassemblycache-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4382-104">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4382-105">구문</span><span class="sxs-lookup"><span data-stu-id="a4382-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4382-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4382-106">Parameters</span></span>  

 `ppAsmCache`  
 <span data-ttu-id="a4382-107">제한이 반환 된 `IAssemblyCache` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4382-107">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="a4382-108">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4382-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a4382-109">`dwReserved` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4382-109">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4382-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4382-110">Requirements</span></span>  

 <span data-ttu-id="a4382-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4382-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4382-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a4382-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a4382-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4382-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4382-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4382-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4382-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4382-115">See also</span></span>

- [<span data-ttu-id="a4382-116">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4382-116">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="a4382-117">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="a4382-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="a4382-118">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="a4382-118">Global Assembly Cache</span></span>](../../app-domains/gac.md)
