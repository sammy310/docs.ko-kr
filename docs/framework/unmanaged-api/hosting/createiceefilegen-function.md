---
title: CreateICeeFileGen 함수
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 294b82efd66704014aab1b73171afe9165f17664
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616452"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="8d276-102">CreateICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="8d276-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="8d276-103">[ICeeFileGen](iceefilegen-class.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d276-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="8d276-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d276-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d276-105">구문</span><span class="sxs-lookup"><span data-stu-id="8d276-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d276-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d276-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="8d276-107">제한이 새 개체의 주소에 대 한 포인터 `ICeeFileGen` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8d276-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d276-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="8d276-108">Return Value</span></span>  
 <span data-ttu-id="8d276-109">이 메서드는 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d276-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d276-110">설명</span><span class="sxs-lookup"><span data-stu-id="8d276-110">Remarks</span></span>  
 <span data-ttu-id="8d276-111">`ICeeFileGen`개체는 CLR (공용 언어 런타임) PE (이식 가능한 실행) 파일을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d276-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="8d276-112">완료 되 면 [DestroyICeeFileGen](destroyiceefilegen-function.md) 함수를 호출 하 여 개체를 삭제 `ICeeFileGen` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d276-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d276-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d276-113">Requirements</span></span>  
 <span data-ttu-id="8d276-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d276-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d276-115">**헤더:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="8d276-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="8d276-116">**라이브러리:** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="8d276-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="8d276-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d276-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d276-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d276-118">See also</span></span>

- [<span data-ttu-id="8d276-119">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="8d276-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
