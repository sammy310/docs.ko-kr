---
title: StrongNameSignatureVerificationEx 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 049b7b11473a05d74dc311ca6ee79947039b0dd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794422"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="f2031-102">StrongNameSignatureVerificationEx 함수</span><span class="sxs-lookup"><span data-stu-id="f2031-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="f2031-103">제공된 경로의 어셈블리 매니페스트에 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="f2031-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-104">This function has been deprecated.</span></span> <span data-ttu-id="f2031-105">사용 된 [iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2031-106">구문</span><span class="sxs-lookup"><span data-stu-id="f2031-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2031-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2031-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f2031-108">[in] 이식 가능한 실행 파일 (.exe 또는.dll) 파일에 확인할 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="f2031-109">[in] `true` 것이 고, 그렇지 않으면 레지스트리 설정을 재정의 해야 하는 경우에 확인 하는 데 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="f2031-110">[out] `true` 강력한 이름 서명을 확인 했으면이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="f2031-111">`pfWasVerified` 또한로 `false` 레지스트리 설정으로 인해 성공 했는지 확인 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="f2031-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2031-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="f2031-112">Return Value</span></span>  
 <span data-ttu-id="f2031-113">`true` 확인에 성공 하면 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2031-114">설명</span><span class="sxs-lookup"><span data-stu-id="f2031-114">Remarks</span></span>  
 <span data-ttu-id="f2031-115">`StrongNameSignatureVerificationEx` 유사한 기능을 제공 합니다 [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="f2031-116">그러나 두 번째 입력 매개 변수와 출력 매개 변수를 `StrongNameSignatureVerificationEx` 형식의 `BOOLEAN` 대신 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2031-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2031-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2031-117">Requirements</span></span>  
 <span data-ttu-id="f2031-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2031-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2031-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f2031-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f2031-120">**라이브러리:** Mscoree.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f2031-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="f2031-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2031-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2031-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2031-122">See also</span></span>

- [<span data-ttu-id="f2031-123">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="f2031-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="f2031-124">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="f2031-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="f2031-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2031-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
