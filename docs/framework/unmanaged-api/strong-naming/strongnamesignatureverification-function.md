---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cd118c302723a7079adbc0dd446d17c8afe9cb6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496770"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="9415f-102">StrongNameSignatureVerification 함수</span><span class="sxs-lookup"><span data-stu-id="9415f-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="9415f-103">제공된 경로의 어셈블리 매니페스트에 지정된 플래그에 따라 확인되는 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="9415f-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-104">This function has been deprecated.</span></span> <span data-ttu-id="9415f-105">사용 된 [iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9415f-106">구문</span><span class="sxs-lookup"><span data-stu-id="9415f-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9415f-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9415f-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9415f-108">[in] 이식 가능한 실행 파일 (.dll 또는.exe) 파일에 어셈블리 확인에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="9415f-109">[in] 확인 동작을 수정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="9415f-110">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-110">The following values are supported:</span></span>  
  
-   <span data-ttu-id="9415f-111">`SN_INFLAG_FORCE_VER` (0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에 확인이 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="9415f-112">`SN_INFLAG_INSTALL` (0x00000002)-매니페스트를 확인 하는 첫 번째 시간 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="9415f-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-캐시는 관리 권한이 있는 사용자만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="9415f-114">`SN_INFLAG_USER_ACCESS` (0x00000008)-어셈블리는 현재 사용자만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="9415f-115">`SN_INFLAG_ALL_ACCESS` (0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="9415f-116">`SN_INFLAG_RUNTIME` (0x80000000)-내부 디버깅을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="9415f-117">[out] 강력한 이름 서명을 확인 하는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="9415f-118">다음 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-118">The following value is supported:</span></span>  
  
-   <span data-ttu-id="9415f-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-이 값 설정할지 `false` 레지스트리 설정으로 인해 확인이 성공 했는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9415f-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="9415f-120">Return Value</span></span>  
 <span data-ttu-id="9415f-121">`true` 확인에 성공 하면 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9415f-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9415f-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9415f-122">Requirements</span></span>  
 <span data-ttu-id="9415f-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9415f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9415f-124">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9415f-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9415f-125">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9415f-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9415f-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9415f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9415f-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="9415f-127">See also</span></span>
- [<span data-ttu-id="9415f-128">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="9415f-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="9415f-129">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="9415f-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="9415f-130">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9415f-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
