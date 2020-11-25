---
title: StrongNameSignatureVerificationFromImage 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
ms.openlocfilehash: b90cc6fe99cf592f1b3fd117888462a957e4ce35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708428"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="e2f32-102">StrongNameSignatureVerificationFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="e2f32-102">StrongNameSignatureVerificationFromImage Function</span></span>

<span data-ttu-id="e2f32-103">메모리에 이미 매핑된 어셈블리가 연결된 공개 키에 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="e2f32-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-104">This function has been deprecated.</span></span> <span data-ttu-id="e2f32-105">대신 [ICLRStrongName:: StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f32-106">구문</span><span class="sxs-lookup"><span data-stu-id="e2f32-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2f32-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2f32-107">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="e2f32-108">진행 매핑된 어셈블리 매니페스트의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e2f32-109">진행 매핑된 이미지의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="e2f32-110">진행 확인 동작에 영향을 주는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="e2f32-111">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="e2f32-112">`SN_INFLAG_FORCE_VER` (0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에도 강제로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="e2f32-113">`SN_INFLAG_INSTALL` (0x00000002)-이 이미지에서 수행 되는 첫 번째 확인을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="e2f32-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004)-캐시가 관리 권한이 있는 사용자 에게만 액세스를 허용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="e2f32-115">`SN_INFLAG_USER_ACCESS` (0x00000008)-현재 사용자만 어셈블리에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="e2f32-116">`SN_INFLAG_ALL_ACCESS` (0x00000010)-캐시가 액세스 제한에 대 한 보장을 제공 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="e2f32-117">`SN_INFLAG_RUNTIME` (0x80000000)-내부 디버깅용으로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="e2f32-118">제한이 추가 출력 정보에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="e2f32-119">지원 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="e2f32-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-이 값은 `false` 레지스트리 설정으로 인해 확인이 성공 하도록 지정 하기 위해로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2f32-121">반환 값</span><span class="sxs-lookup"><span data-stu-id="e2f32-121">Return Value</span></span>  

 <span data-ttu-id="e2f32-122">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2f32-123">설명</span><span class="sxs-lookup"><span data-stu-id="e2f32-123">Remarks</span></span>  

 <span data-ttu-id="e2f32-124">`StrongNameSignatureVerificationFromImage`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2f32-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2f32-125">Requirements</span></span>  

 <span data-ttu-id="e2f32-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2f32-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2f32-127">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="e2f32-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e2f32-128">**라이브러리:** mscoree.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2f32-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="e2f32-129">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2f32-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f32-130">참조</span><span class="sxs-lookup"><span data-stu-id="e2f32-130">See also</span></span>

- [<span data-ttu-id="e2f32-131">StrongNameSignatureVerificationFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="e2f32-131">StrongNameSignatureVerificationFromImage Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="e2f32-132">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2f32-132">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
