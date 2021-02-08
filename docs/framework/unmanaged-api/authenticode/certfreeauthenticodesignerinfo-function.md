---
description: '자세히 알아보기: CertFreeAuthenticodeSignerInfo 함수'
title: CertFreeAuthenticodeSignerInfo 함수
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
topic_type:
- apiref
ms.openlocfilehash: 6e8a97e8fee37d885c7d32102ed8cc7654992223
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772980"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="1cf05-103">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="1cf05-103">CertFreeAuthenticodeSignerInfo Function</span></span>

<span data-ttu-id="1cf05-104">[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조에 할당 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cf05-104">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="1cf05-105">구문</span><span class="sxs-lookup"><span data-stu-id="1cf05-105">Syntax</span></span>

```cpp
HRESULT CertFreeAuthenticodeSignerInfo (
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);
```

## <a name="parameters"></a><span data-ttu-id="1cf05-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1cf05-106">Parameters</span></span>

 `pSignerInfo`\
 <span data-ttu-id="1cf05-107">[in, out] 해제할 서명자 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1cf05-107">[in, out] Signer information to be released.</span></span> <span data-ttu-id="1cf05-108">[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1cf05-108">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>

## <a name="return-value"></a><span data-ttu-id="1cf05-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="1cf05-109">Return Value</span></span>

 <span data-ttu-id="1cf05-110">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="1cf05-110">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="1cf05-111">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cf05-111">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="1cf05-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1cf05-112">Requirements</span></span>

<span data-ttu-id="1cf05-113">**어셈블리**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="1cf05-113">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="1cf05-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cf05-114">See also</span></span>

- [<span data-ttu-id="1cf05-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1cf05-115">Authenticode</span></span>](index.md)
