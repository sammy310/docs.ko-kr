---
description: '자세히 알아보기: StrongNameKeyInstall 함수'
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
ms.openlocfilehash: 0a5d3971ac0927dda7066405adc01a5c80b7faca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670556"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="3062b-103">StrongNameKeyInstall 함수</span><span class="sxs-lookup"><span data-stu-id="3062b-103">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="3062b-104">퍼블릭/프라이빗 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-104">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="3062b-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-105">This function has been deprecated.</span></span> <span data-ttu-id="3062b-106">대신 [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-106">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="3062b-107">구문</span><span class="sxs-lookup"><span data-stu-id="3062b-107">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="3062b-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3062b-108">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="3062b-109">진행 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-109">[in] The name of the key container.</span></span> <span data-ttu-id="3062b-110">`wszKeyContainer` 비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-110">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="3062b-111">진행 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-111">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="3062b-112">진행 의 크기 (바이트)입니다 `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="3062b-112">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3062b-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="3062b-113">Return Value</span></span>

<span data-ttu-id="3062b-114">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-114">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3062b-115">설명</span><span class="sxs-lookup"><span data-stu-id="3062b-115">Remarks</span></span>

<span data-ttu-id="3062b-116">[StrongNameKeyDelete](strongnamekeydelete-function.md) 함수를 사용 하 여 키 컨테이너를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-116">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="3062b-117">`StrongNameKeyInstall`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-117">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="3062b-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3062b-118">Requirements</span></span>

<span data-ttu-id="3062b-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3062b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3062b-120">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="3062b-120">**Header:** StrongName.h</span></span>

<span data-ttu-id="3062b-121">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3062b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="3062b-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3062b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3062b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3062b-123">See also</span></span>

- [<span data-ttu-id="3062b-124">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="3062b-124">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="3062b-125">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="3062b-125">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="3062b-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3062b-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
