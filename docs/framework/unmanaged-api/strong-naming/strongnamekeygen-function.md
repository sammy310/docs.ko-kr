---
title: StrongNameKeyGen 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8ebecce4078ba6c2b59e6bfba2d54300ba0c4ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107382"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="b7b4b-102">StrongNameKeyGen 함수</span><span class="sxs-lookup"><span data-stu-id="b7b4b-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="b7b4b-103">강력한 이름 사용을 위한 새 공개/개인 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="b7b4b-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-104">This function has been deprecated.</span></span> <span data-ttu-id="b7b4b-105">사용 된 [iclrstrongname:: Strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b4b-106">구문</span><span class="sxs-lookup"><span data-stu-id="b7b4b-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7b4b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7b4b-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="b7b4b-108">[in] 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-108">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="b7b4b-109">비어 있지 않은 문자열 이어야 하거나 null로 임시 이름을 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-109">must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b7b4b-110">[in] 등록 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="b7b4b-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="b7b4b-112">때 사용 되는 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="b7b4b-113">0x00000001 (`SN_LEAVE_KEY`)-키 왼쪽 등록 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="b7b4b-114">[out] 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="b7b4b-115">[out] 크기 (바이트)의 `ppbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7b4b-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="b7b4b-116">Return Value</span></span>  
 `true` <span data-ttu-id="b7b4b-117">성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-117">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7b4b-118">설명</span><span class="sxs-lookup"><span data-stu-id="b7b4b-118">Remarks</span></span>  
 <span data-ttu-id="b7b4b-119">`StrongNameKeyGen` 함수 1024 비트 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="b7b4b-120">키 검색 되 면 호출 해야 합니다 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 할당 된 메모리를 해제 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="b7b4b-121">경우는 `StrongNameKeyGen` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b4b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7b4b-122">Requirements</span></span>  
 <span data-ttu-id="b7b4b-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7b4b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b4b-124">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b7b4b-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b7b4b-125">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b7b4b-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b7b4b-126">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b7b4b-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7b4b-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7b4b-127">See also</span></span>

- [<span data-ttu-id="b7b4b-128">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="b7b4b-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="b7b4b-129">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="b7b4b-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="b7b4b-130">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7b4b-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
