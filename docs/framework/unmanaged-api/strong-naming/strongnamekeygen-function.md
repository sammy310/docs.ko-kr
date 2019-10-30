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
ms.openlocfilehash: 79b2235e3645c89c2cd9ebcce079d5eb7efdd162
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128746"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="a9e52-102">StrongNameKeyGen 함수</span><span class="sxs-lookup"><span data-stu-id="a9e52-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="a9e52-103">강력한 이름 사용을 위한 새 퍼블릭/프라이빗 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="a9e52-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-104">This function has been deprecated.</span></span> <span data-ttu-id="a9e52-105">대신 [ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9e52-106">구문</span><span class="sxs-lookup"><span data-stu-id="a9e52-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9e52-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9e52-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="a9e52-108">진행 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-108">[in] The requested key container name.</span></span> <span data-ttu-id="a9e52-109">`wszKeyContainer`은 비어 있지 않은 문자열 이거나 null 이거나 임시 이름을 생성 하는 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a9e52-110">진행 키를 등록 된 상태로 유지할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="a9e52-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="a9e52-112">0x00000000-임시 키 컨테이너 이름을 생성 하기 위해 `wszKeyContainer`가 null 일 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="a9e52-113">0x00000001 (`SN_LEAVE_KEY`)-키를 등록 된 상태로 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="a9e52-114">제한이 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="a9e52-115">제한이 `ppbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9e52-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="a9e52-116">Return Value</span></span>  
 <span data-ttu-id="a9e52-117">성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9e52-118">주의</span><span class="sxs-lookup"><span data-stu-id="a9e52-118">Remarks</span></span>  
 <span data-ttu-id="a9e52-119">`StrongNameKeyGen` 함수는 1024 비트 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="a9e52-120">키를 검색 한 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="a9e52-121">`StrongNameKeyGen` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9e52-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9e52-122">Requirements</span></span>  
 <span data-ttu-id="a9e52-123">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9e52-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9e52-124">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="a9e52-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a9e52-125">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e52-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9e52-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9e52-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e52-127">참조</span><span class="sxs-lookup"><span data-stu-id="a9e52-127">See also</span></span>

- [<span data-ttu-id="a9e52-128">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="a9e52-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="a9e52-129">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="a9e52-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="a9e52-130">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9e52-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
