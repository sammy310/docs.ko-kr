---
title: ICLRStrongName::StrongNameKeyGen 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: 4f3574e282d24fa11ffa2f85463f682c42098ae7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135048"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="1f162-102">ICLRStrongName::StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="1f162-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="1f162-103">강력한 이름 사용을 위한 새 퍼블릭/프라이빗 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f162-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f162-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f162-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f162-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="1f162-106">진행 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-106">[in] The requested key container name.</span></span> <span data-ttu-id="1f162-107">임시 이름을 생성 하려면 `wszKeyContainer`은 비어 있지 않은 문자열 이거나 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1f162-108">진행 키를 등록 된 상태로 유지할지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="1f162-109">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="1f162-110">0x00000000-임시 키 컨테이너 이름을 생성 하기 위해 `wszKeyContainer`가 null 일 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="1f162-111">0x00000001 (`SN_LEAVE_KEY`)-키를 등록 된 상태로 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="1f162-112">제한이 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="1f162-113">제한이 `ppbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f162-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f162-114">Return Value</span></span>  
 <span data-ttu-id="1f162-115">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).</span><span class="sxs-lookup"><span data-stu-id="1f162-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f162-116">주의</span><span class="sxs-lookup"><span data-stu-id="1f162-116">Remarks</span></span>  
 <span data-ttu-id="1f162-117">[ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) 메서드는 1024 비트 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="1f162-118">키를 검색 한 후에는 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f162-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f162-119">Requirements</span></span>  
 <span data-ttu-id="1f162-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f162-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f162-121">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="1f162-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1f162-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f162-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f162-123">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f162-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f162-124">참조</span><span class="sxs-lookup"><span data-stu-id="1f162-124">See also</span></span>

- [<span data-ttu-id="1f162-125">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="1f162-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="1f162-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f162-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
