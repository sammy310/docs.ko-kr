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
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799003"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="234c9-102">StrongNameKeyInstall 함수</span><span class="sxs-lookup"><span data-stu-id="234c9-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="234c9-103">퍼블릭/프라이빗 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="234c9-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-104">This function has been deprecated.</span></span> <span data-ttu-id="234c9-105">대신 [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="234c9-106">구문</span><span class="sxs-lookup"><span data-stu-id="234c9-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="234c9-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="234c9-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="234c9-108">진행 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-108">[in] The name of the key container.</span></span> <span data-ttu-id="234c9-109">`wszKeyContainer`비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="234c9-110">진행 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="234c9-111">진행 의 `pbKeyBlob`크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="234c9-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="234c9-112">Return Value</span></span>

<span data-ttu-id="234c9-113">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="234c9-114">설명</span><span class="sxs-lookup"><span data-stu-id="234c9-114">Remarks</span></span>

<span data-ttu-id="234c9-115">[StrongNameKeyDelete](strongnamekeydelete-function.md) 함수를 사용 하 여 키 컨테이너를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="234c9-116">`StrongNameKeyInstall`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="234c9-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="234c9-117">Requirements</span></span>

<span data-ttu-id="234c9-118">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="234c9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="234c9-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="234c9-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="234c9-120">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="234c9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="234c9-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="234c9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="234c9-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="234c9-122">See also</span></span>

- [<span data-ttu-id="234c9-123">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="234c9-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="234c9-124">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="234c9-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="234c9-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="234c9-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
