---
title: StrongNameKeyGenEx 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af75a645b11325b96740807f9a3df65f5a676026
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120863"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="724e5-102">StrongNameKeyGenEx 함수</span><span class="sxs-lookup"><span data-stu-id="724e5-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="724e5-103">강력한 이름 사용에 대 한 지정된 된 키 크기를 사용 하 여 새 공개/개인 키 쌍을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="724e5-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-104">This function has been deprecated.</span></span> <span data-ttu-id="724e5-105">사용 된 [iclrstrongname:: Strongnamekeygenex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="724e5-106">구문</span><span class="sxs-lookup"><span data-stu-id="724e5-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="724e5-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="724e5-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="724e5-108">[in] 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-108">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="724e5-109">비어 있지 않은 문자열 이어야 하거나 null로 임시 이름을 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-109">must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="724e5-110">[in] 등록 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="724e5-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="724e5-112">때 사용 되는 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="724e5-113">0x00000001 (`SN_LEAVE_KEY`)-키 왼쪽 등록 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="724e5-114">[in] 비트에서 키의 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="724e5-115">[out] 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="724e5-116">[out] 크기 (바이트)의 `ppbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="724e5-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="724e5-117">Return Value</span></span>  
 `true` <span data-ttu-id="724e5-118">성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-118">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="724e5-119">설명</span><span class="sxs-lookup"><span data-stu-id="724e5-119">Remarks</span></span>  
 <span data-ttu-id="724e5-120">.NET Framework 버전 1.0 및 1.1 필요는 `dwKeySize` ; 강력한 이름의 어셈블리에 서명할 1024 비트의 버전 2.0는 2048 비트 키에 대 한 지원 추가.</span><span class="sxs-lookup"><span data-stu-id="724e5-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="724e5-121">키 검색 되 면 호출 해야 합니다 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 할당 된 메모리를 해제 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="724e5-122">경우는 `StrongNameKeyGenEx` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="724e5-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="724e5-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="724e5-123">Requirements</span></span>  
 <span data-ttu-id="724e5-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="724e5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="724e5-125">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="724e5-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="724e5-126">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="724e5-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="724e5-127">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="724e5-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="724e5-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="724e5-128">See also</span></span>

- [<span data-ttu-id="724e5-129">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="724e5-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="724e5-130">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="724e5-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="724e5-131">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="724e5-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
