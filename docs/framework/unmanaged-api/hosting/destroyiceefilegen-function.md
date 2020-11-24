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
ms.openlocfilehash: 495d84470c559df13ea64b63dd00582f4335d4e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673195"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="6cb44-102">DestroyICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="6cb44-102">DestroyICeeFileGen Function</span></span>

<span data-ttu-id="6cb44-103">[ICeeFileGen](iceefilegen-class.md) 개체를 소멸 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6cb44-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="6cb44-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb44-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cb44-105">구문</span><span class="sxs-lookup"><span data-stu-id="6cb44-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cb44-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6cb44-106">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="6cb44-107">진행 `ICeeFileGen` 제거할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb44-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cb44-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6cb44-108">Return Value</span></span>  

 <span data-ttu-id="6cb44-109">이 메서드는 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb44-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cb44-110">설명</span><span class="sxs-lookup"><span data-stu-id="6cb44-110">Remarks</span></span>  

 <span data-ttu-id="6cb44-111">`DestroyICeeFileGen``ICeeFileGen` [CreateICeeFileGen](createiceefilegen-function.md) 함수에서 만든 개체를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb44-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cb44-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6cb44-112">Requirements</span></span>  

 <span data-ttu-id="6cb44-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb44-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cb44-114">**헤더:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="6cb44-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="6cb44-115">**라이브러리:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="6cb44-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="6cb44-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cb44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb44-117">참조</span><span class="sxs-lookup"><span data-stu-id="6cb44-117">See also</span></span>

- [<span data-ttu-id="6cb44-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="6cb44-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
