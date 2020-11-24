---
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
ms.openlocfilehash: 3197c650b4f167e7a5043270797d2c4a62413d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683201"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="87a21-102">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="87a21-102">CreateAssemblyCache Function</span></span>

<span data-ttu-id="87a21-103">전역 어셈블리 캐시를 나타내는 새 [Iassemblycache](iassemblycache-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87a21-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a21-104">구문</span><span class="sxs-lookup"><span data-stu-id="87a21-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="87a21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87a21-105">Parameters</span></span>  

 `ppAsmCache`  
 <span data-ttu-id="87a21-106">제한이 반환 된 `IAssemblyCache` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87a21-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="87a21-107">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87a21-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="87a21-108">`dwReserved` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a21-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87a21-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87a21-109">Requirements</span></span>  

 <span data-ttu-id="87a21-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87a21-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87a21-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="87a21-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="87a21-112">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a21-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87a21-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87a21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a21-114">참조</span><span class="sxs-lookup"><span data-stu-id="87a21-114">See also</span></span>

- [<span data-ttu-id="87a21-115">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87a21-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="87a21-116">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="87a21-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="87a21-117">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="87a21-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
