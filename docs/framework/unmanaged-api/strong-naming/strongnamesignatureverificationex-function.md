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
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798921"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="67c9e-102">StrongNameSignatureVerificationEx 함수</span><span class="sxs-lookup"><span data-stu-id="67c9e-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="67c9e-103">제공된 경로의 어셈블리 매니페스트에 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="67c9e-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-104">This function has been deprecated.</span></span> <span data-ttu-id="67c9e-105">대신 [ICLRStrongName:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c9e-106">구문</span><span class="sxs-lookup"><span data-stu-id="67c9e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67c9e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67c9e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="67c9e-108">진행 확인할 어셈블리의 이식 가능한 실행 파일 (.exe 또는 .dll) 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="67c9e-109">진행 레지스트리 설정을 재정의 해야 하는 경우에도 유효성 검사를 수행 하려면이 고 `false`, 그렇지 않으면입니다. `true`</span><span class="sxs-lookup"><span data-stu-id="67c9e-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="67c9e-110">제한이 강력한 이름 서명을 확인 했으면이 고, `false`그렇지 않으면입니다. `true`</span><span class="sxs-lookup"><span data-stu-id="67c9e-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="67c9e-111">`pfWasVerified`레지스트리 설정으로 인해 `false` 확인이 성공적으로 수행 된 경우에도로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67c9e-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="67c9e-112">Return Value</span></span>  
 <span data-ttu-id="67c9e-113">`true`확인에 성공 했으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c9e-114">설명</span><span class="sxs-lookup"><span data-stu-id="67c9e-114">Remarks</span></span>  
 <span data-ttu-id="67c9e-115">`StrongNameSignatureVerificationEx`[StrongNameSignatureVerification](strongnamesignatureverification-function.md) 함수와 비슷한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="67c9e-116">그러나에 대 한 `StrongNameSignatureVerificationEx` 두 번째 입력 매개 변수 및 출력 매개 변수는 대신 `DWORD`형식 `BOOLEAN` 입니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c9e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67c9e-117">Requirements</span></span>  
 <span data-ttu-id="67c9e-118">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67c9e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c9e-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="67c9e-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="67c9e-120">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67c9e-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="67c9e-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c9e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c9e-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="67c9e-122">See also</span></span>

- [<span data-ttu-id="67c9e-123">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="67c9e-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="67c9e-124">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="67c9e-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="67c9e-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67c9e-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
