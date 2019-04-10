---
title: ICLRStrongName::StrongNameSignatureVerification 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9fb7098c29768821cafad6662b646eb0e08a138
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212845"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="c6eb7-102">ICLRStrongName::StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="c6eb7-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="c6eb7-103">어셈블리 매니페스트에 제공 된 경로의 지정된 된 플래그에 따라 확인할 수 있는 강력한 이름 서명을 포함 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6eb7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6eb7-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6eb7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6eb7-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c6eb7-106">[in] 이식 가능한 실행 파일 (.dll 또는.exe) 파일에 어셈블리 확인에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="c6eb7-107">[in] 확인 동작을 수정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="c6eb7-108">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-108">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="c6eb7-109">(0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에 확인이 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-109">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="c6eb7-110">(0x00000002)-매니페스트를 확인 하는 첫 번째 시간 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-110">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="c6eb7-111">(0x00000004)-캐시는 관리 권한이 있는 사용자만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-111">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="c6eb7-112">(0x00000008)-어셈블리는 현재 사용자만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-112">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="c6eb7-113">(0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-113">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="c6eb7-114">(0x80000000)-내부 디버깅을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-114">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="c6eb7-115">[out] 강력한 이름 서명을 확인 하는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="c6eb7-116">다음 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-116">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="c6eb7-117">(0x00000001)-이 값 설정할지 `false` 레지스트리 설정으로 인해 확인이 성공 했는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-117">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6eb7-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="c6eb7-118">Return Value</span></span>  
 `S_OK` <span data-ttu-id="c6eb7-119">메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="c6eb7-119">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6eb7-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6eb7-120">Requirements</span></span>  
 <span data-ttu-id="c6eb7-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6eb7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6eb7-122">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c6eb7-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c6eb7-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c6eb7-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c6eb7-124">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="c6eb7-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6eb7-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6eb7-125">See also</span></span>

- [<span data-ttu-id="c6eb7-126">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="c6eb7-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="c6eb7-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6eb7-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
