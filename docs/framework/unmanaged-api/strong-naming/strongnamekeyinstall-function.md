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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3fc69b2edf611383402b13555cf33be10dbad3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000391"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="6a80e-102">StrongNameKeyInstall 함수</span><span class="sxs-lookup"><span data-stu-id="6a80e-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="6a80e-103">공개/개인 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="6a80e-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-104">This function has been deprecated.</span></span> <span data-ttu-id="6a80e-105">사용 된 [iclrstrongname:: Strongnamekeyinstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a80e-106">구문</span><span class="sxs-lookup"><span data-stu-id="6a80e-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="6a80e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a80e-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="6a80e-108">[in] 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-108">[in] The name of the key container.</span></span> <span data-ttu-id="6a80e-109">`wszKeyContainer` 비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="6a80e-110">[in] 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="6a80e-111">[in] 크기 (바이트)의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="6a80e-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="6a80e-112">Return Value</span></span>

<span data-ttu-id="6a80e-113">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a80e-114">설명</span><span class="sxs-lookup"><span data-stu-id="6a80e-114">Remarks</span></span>

<span data-ttu-id="6a80e-115">사용 된 [StrongNameKeyDelete](strongnamekeydelete-function.md) 키 컨테이너를 삭제 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="6a80e-116">경우는 `StrongNameKeyInstall` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a80e-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a80e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a80e-117">Requirements</span></span>

<span data-ttu-id="6a80e-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a80e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6a80e-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6a80e-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="6a80e-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6a80e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="6a80e-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a80e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6a80e-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a80e-122">See also</span></span>

- [<span data-ttu-id="6a80e-123">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="6a80e-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="6a80e-124">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="6a80e-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="6a80e-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a80e-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)