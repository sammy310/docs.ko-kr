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
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899549"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="992b1-102">ICLRStrongName::StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="992b1-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="992b1-103">강력한 이름 사용을 위해 지정 된 키 크기를 사용 하 여 새 공개/개인 키 쌍을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="992b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="992b1-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="992b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="992b1-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="992b1-106">진행 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-106">[in] The requested key container name.</span></span> <span data-ttu-id="992b1-107">임시 이름을 생성 하려면 `wszKeyContainer`은 비어 있지 않은 문자열 이거나 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="992b1-108">진행 키를 등록 된 상태로 유지할지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="992b1-109">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="992b1-110">0x00000000-임시 키 컨테이너 이름을 생성 하기 위해 `wszKeyContainer`가 null 일 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="992b1-111">0x00000001 (`SN_LEAVE_KEY`)-키를 등록 된 상태로 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="992b1-112">진행 요청 된 키 크기 (비트)입니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="992b1-113">제한이 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="992b1-114">제한이 `ppbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="992b1-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="992b1-115">Return Value</span></span>  
 <span data-ttu-id="992b1-116">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="992b1-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="992b1-117">주의</span><span class="sxs-lookup"><span data-stu-id="992b1-117">Remarks</span></span>  
 <span data-ttu-id="992b1-118">.NET Framework 버전 1.0 및 1.1에는 강력한 이름의 어셈블리에 서명 하는 데 1024 비트의 `dwKeySize` 필요 합니다. 버전 2.0에는 2048 비트 키에 대 한 지원 기능이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="992b1-119">키를 검색 한 후에는 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="992b1-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="992b1-120">Requirements</span></span>  
 <span data-ttu-id="992b1-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="992b1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="992b1-122">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="992b1-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="992b1-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="992b1-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="992b1-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="992b1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="992b1-125">참조</span><span class="sxs-lookup"><span data-stu-id="992b1-125">See also</span></span>

- [<span data-ttu-id="992b1-126">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="992b1-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="992b1-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="992b1-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
