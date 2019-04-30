---
title: ICLRStrongName::StrongNameKeyGenEx 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97e6f16029b9a273a68d52b830939819bfa5380
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993033"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="2074e-102">ICLRStrongName::StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="2074e-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="2074e-103">강력한 이름 사용에 대 한 지정된 된 키 크기를 사용 하 여 새 공개/개인 키 쌍을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2074e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2074e-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2074e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2074e-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="2074e-106">[in] 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-106">[in] The requested key container name.</span></span> <span data-ttu-id="2074e-107">`wszKeyContainer` 비어 있지 않은 문자열 또는 임시 이름을 생성 하는 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2074e-108">[in] 등록 키를 유지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="2074e-109">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="2074e-110">때 사용 되는 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="2074e-111">0x00000001 (`SN_LEAVE_KEY`)-키 왼쪽 등록 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="2074e-112">[in] 비트에서 키의 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="2074e-113">[out] 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="2074e-114">[out] 크기 (바이트)의 `ppbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2074e-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="2074e-115">Return Value</span></span>  
 <span data-ttu-id="2074e-116">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="2074e-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2074e-117">설명</span><span class="sxs-lookup"><span data-stu-id="2074e-117">Remarks</span></span>  
 <span data-ttu-id="2074e-118">.NET Framework 버전 1.0 및 1.1 필요는 `dwKeySize` ; 강력한 이름의 어셈블리에 서명할 1024 비트의 버전 2.0는 2048 비트 키에 대 한 지원 추가.</span><span class="sxs-lookup"><span data-stu-id="2074e-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="2074e-119">키 검색 되 면 호출 해야 합니다 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 할당 된 메모리를 해제 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2074e-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2074e-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2074e-120">Requirements</span></span>  
 <span data-ttu-id="2074e-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2074e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2074e-122">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2074e-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2074e-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2074e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2074e-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2074e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2074e-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="2074e-125">See also</span></span>

- [<span data-ttu-id="2074e-126">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="2074e-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="2074e-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2074e-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
