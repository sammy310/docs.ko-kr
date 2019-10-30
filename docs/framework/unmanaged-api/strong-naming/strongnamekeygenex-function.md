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
ms.openlocfilehash: 63ddd90f3a8090853d10f03052915d10e1503ea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125212"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="873e2-102">StrongNameKeyGenEx 함수</span><span class="sxs-lookup"><span data-stu-id="873e2-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="873e2-103">강력한 이름 사용을 위해 지정 된 키 크기를 사용 하 여 새 공개/개인 키 쌍을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="873e2-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-104">This function has been deprecated.</span></span> <span data-ttu-id="873e2-105">대신 [ICLRStrongName:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873e2-106">구문</span><span class="sxs-lookup"><span data-stu-id="873e2-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="873e2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="873e2-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="873e2-108">진행 요청 된 키 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-108">[in] The requested key container name.</span></span> <span data-ttu-id="873e2-109">`wszKeyContainer`은 비어 있지 않은 문자열 이거나 null 이거나 임시 이름을 생성 하는 null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="873e2-110">진행 키를 등록 된 상태로 유지할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="873e2-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="873e2-112">0x00000000-임시 키 컨테이너 이름을 생성 하기 위해 `wszKeyContainer`가 null 일 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="873e2-113">0x00000001 (`SN_LEAVE_KEY`)-키를 등록 된 상태로 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="873e2-114">진행 요청 된 키 크기 (비트)입니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="873e2-115">제한이 반환 된 공개/개인 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="873e2-116">제한이 `ppbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="873e2-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="873e2-117">Return Value</span></span>  
 <span data-ttu-id="873e2-118">성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="873e2-119">주의</span><span class="sxs-lookup"><span data-stu-id="873e2-119">Remarks</span></span>  
 <span data-ttu-id="873e2-120">.NET Framework 버전 1.0 및 1.1에는 강력한 이름의 어셈블리에 서명 하는 데 1024 비트의 `dwKeySize` 필요 합니다. 버전 2.0에는 2048 비트 키에 대 한 지원 기능이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="873e2-121">키를 검색 한 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="873e2-122">`StrongNameKeyGenEx` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="873e2-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="873e2-123">Requirements</span></span>  
 <span data-ttu-id="873e2-124">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="873e2-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="873e2-125">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="873e2-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="873e2-126">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="873e2-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="873e2-127">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="873e2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873e2-128">참조</span><span class="sxs-lookup"><span data-stu-id="873e2-128">See also</span></span>

- [<span data-ttu-id="873e2-129">StrongNameKeyGenEx 메서드</span><span class="sxs-lookup"><span data-stu-id="873e2-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="873e2-130">StrongNameKeyGen 메서드</span><span class="sxs-lookup"><span data-stu-id="873e2-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="873e2-131">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="873e2-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
