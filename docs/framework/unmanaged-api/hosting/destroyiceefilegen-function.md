---
description: '자세히 알아보기: DestroyICeeFileGen 함수'
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
ms.openlocfilehash: 14ae990999247b90f16b10115dea3408b965a04a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785655"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="8b611-103">DestroyICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="8b611-103">DestroyICeeFileGen Function</span></span>

<span data-ttu-id="8b611-104">[ICeeFileGen](iceefilegen-class.md) 개체를 소멸 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8b611-104">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="8b611-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b611-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b611-106">구문</span><span class="sxs-lookup"><span data-stu-id="8b611-106">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b611-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b611-107">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="8b611-108">진행 `ICeeFileGen` 제거할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8b611-108">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b611-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="8b611-109">Return Value</span></span>  

 <span data-ttu-id="8b611-110">이 메서드는 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b611-110">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b611-111">설명</span><span class="sxs-lookup"><span data-stu-id="8b611-111">Remarks</span></span>  

 <span data-ttu-id="8b611-112">`DestroyICeeFileGen``ICeeFileGen` [CreateICeeFileGen](createiceefilegen-function.md) 함수에서 만든 개체를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b611-112">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b611-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b611-113">Requirements</span></span>  

 <span data-ttu-id="8b611-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b611-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b611-115">**헤더:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="8b611-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="8b611-116">**라이브러리:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="8b611-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="8b611-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b611-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b611-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b611-118">See also</span></span>

- [<span data-ttu-id="8b611-119">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="8b611-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
