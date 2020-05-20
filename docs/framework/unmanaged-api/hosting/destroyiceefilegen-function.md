---
title: DestroyICeeFileGen 함수
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: ff7e7b299d185b8db263d2076c1e075b87b487fc
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616400"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="9cbfb-102">DestroyICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="9cbfb-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="9cbfb-103">[ICeeFileGen](iceefilegen-class.md) 개체를 소멸 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9cbfb-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="9cbfb-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cbfb-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cbfb-105">구문</span><span class="sxs-lookup"><span data-stu-id="9cbfb-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cbfb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9cbfb-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="9cbfb-107">진행 `ICeeFileGen`제거할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9cbfb-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cbfb-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="9cbfb-108">Return Value</span></span>  
 <span data-ttu-id="9cbfb-109">이 메서드는 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbfb-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cbfb-110">설명</span><span class="sxs-lookup"><span data-stu-id="9cbfb-110">Remarks</span></span>  
 <span data-ttu-id="9cbfb-111">`DestroyICeeFileGen``ICeeFileGen` [CreateICeeFileGen](createiceefilegen-function.md) 함수에서 만든 개체를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cbfb-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cbfb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9cbfb-112">Requirements</span></span>  
 <span data-ttu-id="9cbfb-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cbfb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cbfb-114">**헤더:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="9cbfb-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="9cbfb-115">**라이브러리:** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="9cbfb-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="9cbfb-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cbfb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbfb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cbfb-117">See also</span></span>

- [<span data-ttu-id="9cbfb-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="9cbfb-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
