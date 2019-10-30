---
title: StrongNameKeyInstall 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125203"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="bf757-102">StrongNameKeyInstall 함수</span><span class="sxs-lookup"><span data-stu-id="bf757-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="bf757-103">퍼블릭/프라이빗 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="bf757-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-104">This function has been deprecated.</span></span> <span data-ttu-id="bf757-105">대신 [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf757-106">구문</span><span class="sxs-lookup"><span data-stu-id="bf757-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="bf757-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf757-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="bf757-108">진행 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-108">[in] The name of the key container.</span></span> <span data-ttu-id="bf757-109">`wszKeyContainer`은 비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="bf757-110">진행 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="bf757-111">진행 `pbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="bf757-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="bf757-112">Return Value</span></span>

<span data-ttu-id="bf757-113">성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf757-114">주의</span><span class="sxs-lookup"><span data-stu-id="bf757-114">Remarks</span></span>

<span data-ttu-id="bf757-115">[StrongNameKeyDelete](strongnamekeydelete-function.md) 함수를 사용 하 여 키 컨테이너를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="bf757-116">`StrongNameKeyInstall` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf757-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf757-117">Requirements</span></span>

<span data-ttu-id="bf757-118">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf757-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bf757-119">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="bf757-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="bf757-120">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf757-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="bf757-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf757-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bf757-122">참조</span><span class="sxs-lookup"><span data-stu-id="bf757-122">See also</span></span>

- [<span data-ttu-id="bf757-123">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="bf757-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="bf757-124">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="bf757-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="bf757-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf757-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
