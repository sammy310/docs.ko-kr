---
description: '자세히 알아보기: CreateICeeFileGen 함수'
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
ms.openlocfilehash: 10aefaad4dd1173e4ef55f727371bab508e2d40c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716932"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="1ba71-103">CreateICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="1ba71-103">CreateICeeFileGen Function</span></span>

<span data-ttu-id="1ba71-104">[ICeeFileGen](iceefilegen-class.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1ba71-104">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="1ba71-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba71-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba71-106">구문</span><span class="sxs-lookup"><span data-stu-id="1ba71-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ba71-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ba71-107">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="1ba71-108">제한이 새 개체의 주소에 대 한 포인터 `ICeeFileGen` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1ba71-108">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ba71-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="1ba71-109">Return Value</span></span>  

 <span data-ttu-id="1ba71-110">이 메서드는 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba71-110">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ba71-111">설명</span><span class="sxs-lookup"><span data-stu-id="1ba71-111">Remarks</span></span>  

 <span data-ttu-id="1ba71-112">`ICeeFileGen`개체는 CLR (공용 언어 런타임) PE (이식 가능한 실행) 파일을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ba71-112">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="1ba71-113">완료 되 면 [DestroyICeeFileGen](destroyiceefilegen-function.md) 함수를 호출 하 여 개체를 삭제 `ICeeFileGen` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba71-113">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba71-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ba71-114">Requirements</span></span>  

 <span data-ttu-id="1ba71-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ba71-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba71-116">**헤더:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="1ba71-116">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="1ba71-117">**라이브러리:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="1ba71-117">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="1ba71-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba71-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba71-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ba71-119">See also</span></span>

- [<span data-ttu-id="1ba71-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="1ba71-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
