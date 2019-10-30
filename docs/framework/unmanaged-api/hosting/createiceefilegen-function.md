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
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136833"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="98961-102">CreateICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="98961-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="98961-103">[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98961-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="98961-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98961-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98961-105">구문</span><span class="sxs-lookup"><span data-stu-id="98961-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98961-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98961-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="98961-107">제한이 새 `ICeeFileGen` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="98961-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98961-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="98961-108">Return Value</span></span>  
 <span data-ttu-id="98961-109">이 메서드는 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="98961-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98961-110">주의</span><span class="sxs-lookup"><span data-stu-id="98961-110">Remarks</span></span>  
 <span data-ttu-id="98961-111">`ICeeFileGen` 개체는 CLR (공용 언어 런타임) PE (이식 가능한 실행) 파일을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98961-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="98961-112">완료 되 면 [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) 함수를 호출 하 여 `ICeeFileGen` 개체를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="98961-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98961-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98961-113">Requirements</span></span>  
 <span data-ttu-id="98961-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98961-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98961-115">**헤더:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="98961-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="98961-116">**라이브러리:** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="98961-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="98961-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98961-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98961-118">참조</span><span class="sxs-lookup"><span data-stu-id="98961-118">See also</span></span>

- [<span data-ttu-id="98961-119">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="98961-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
