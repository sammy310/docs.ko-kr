---
description: '자세히 알아보기: ICLRStrongName:: StrongNameKeyGen 메서드'
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
ms.openlocfilehash: c445e1f0290d907f7820c0000f602f2668f59103
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799562"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="b440e-103">ICLRStrongName::StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="b440e-103">ICLRStrongName::StrongNameKeyGen Method</span></span>

<span data-ttu-id="b440e-104">강력한 이름 사용을 위한 새 퍼블릭/프라이빗 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-104">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b440e-105">구문</span><span class="sxs-lookup"><span data-stu-id="b440e-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b440e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b440e-106">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="b440e-107">진행 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-107">[in] The requested key container name.</span></span> <span data-ttu-id="b440e-108">`wszKeyContainer` 임시 이름을 생성 하려면 비어 있지 않은 문자열 이거나 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-108">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b440e-109">진행 키를 등록 된 상태로 유지할지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-109">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="b440e-110">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="b440e-111">0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하기 위해가 null 일 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-111">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="b440e-112">0x00000001 ( `SN_LEAVE_KEY` )-키를 등록 된 상태로 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-112">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="b440e-113">제한이 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="b440e-114">제한이 의 크기 (바이트)입니다 `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="b440e-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b440e-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="b440e-115">Return Value</span></span>  

 <span data-ttu-id="b440e-116">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="b440e-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b440e-117">설명</span><span class="sxs-lookup"><span data-stu-id="b440e-117">Remarks</span></span>  

 <span data-ttu-id="b440e-118">[ICLRStrongName:: StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) 메서드는 1024 비트 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-118">The [ICLRStrongName::StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="b440e-119">키를 검색 한 후에는 [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) 메서드를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b440e-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b440e-120">Requirements</span></span>  

 <span data-ttu-id="b440e-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b440e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b440e-122">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="b440e-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b440e-123">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b440e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b440e-124">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b440e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b440e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b440e-125">See also</span></span>

- [<span data-ttu-id="b440e-126">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="b440e-126">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="b440e-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b440e-127">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
