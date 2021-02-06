---
description: '자세히 알아보기: StrongNameSignatureVerification 함수'
title: StrongNameSignatureVerification 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
ms.openlocfilehash: 74130cda96f38218d2fd296ff8804f86a9a18cd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636263"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="8dd35-103">StrongNameSignatureVerification 함수</span><span class="sxs-lookup"><span data-stu-id="8dd35-103">StrongNameSignatureVerification Function</span></span>

<span data-ttu-id="8dd35-104">제공된 경로의 어셈블리 매니페스트에 지정된 플래그에 따라 확인되는 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-104">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="8dd35-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-105">This function has been deprecated.</span></span> <span data-ttu-id="8dd35-106">대신 [ICLRStrongName:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-106">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dd35-107">구문</span><span class="sxs-lookup"><span data-stu-id="8dd35-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dd35-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8dd35-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="8dd35-109">진행 어셈블리에서 확인할 이식 가능한 실행 파일 (.dll 또는 .exe)의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-109">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="8dd35-110">진행 확인 동작을 수정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-110">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="8dd35-111">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="8dd35-112">`SN_INFLAG_FORCE_VER` (0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에도 강제로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="8dd35-113">`SN_INFLAG_INSTALL` (0x00000002)-매니페스트를 처음 확인 하는 것을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="8dd35-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-캐시가 관리 권한이 있는 사용자 에게만 액세스를 허용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="8dd35-115">`SN_INFLAG_USER_ACCESS` (0x00000008)-현재 사용자만 어셈블리에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="8dd35-116">`SN_INFLAG_ALL_ACCESS` (0x00000010)-캐시가 액세스 제한에 대 한 보장을 제공 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="8dd35-117">`SN_INFLAG_RUNTIME` (0x80000000)-내부 디버깅용으로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="8dd35-118">제한이 강력한 이름 서명을 확인 했는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-118">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="8dd35-119">지원 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="8dd35-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-이 값은 `false` 레지스트리 설정으로 인해 확인이 성공 하도록 지정 하기 위해로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dd35-121">Return Value</span><span class="sxs-lookup"><span data-stu-id="8dd35-121">Return Value</span></span>  

 <span data-ttu-id="8dd35-122">`true` 확인에 성공 했으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-122">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dd35-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8dd35-123">Requirements</span></span>  

 <span data-ttu-id="8dd35-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dd35-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dd35-125">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="8dd35-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8dd35-126">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd35-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8dd35-127">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dd35-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd35-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dd35-128">See also</span></span>

- [<span data-ttu-id="8dd35-129">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="8dd35-129">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="8dd35-130">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="8dd35-130">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="8dd35-131">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8dd35-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
