---
description: '자세히 알아보기: CertFreeAuthenticodeTimestamperInfo 함수'
title: CertFreeAuthenticodeTimestamperInfo 함수
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
topic_type:
- apiref
ms.openlocfilehash: 5234a90ea1d0272a7409b1b0b4def2160b77a513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772941"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="2c37b-103">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="2c37b-103">CertFreeAuthenticodeTimestamperInfo Function</span></span>

<span data-ttu-id="2c37b-104">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) 구조에 할당 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c37b-104">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c37b-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c37b-105">Syntax</span></span>

```cpp
HRESULT CertFreeAuthenticodeTimestamperInfo (
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo
);
```

## <a name="parameters"></a><span data-ttu-id="2c37b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c37b-106">Parameters</span></span>

 `pTimestamperInfo`\
 <span data-ttu-id="2c37b-107">[in, out] 해제할 타임스탬퍼 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="2c37b-107">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="2c37b-108">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c37b-108">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>

## <a name="return-value"></a><span data-ttu-id="2c37b-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="2c37b-109">Return Value</span></span>

 <span data-ttu-id="2c37b-110">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="2c37b-110">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="2c37b-111">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c37b-111">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c37b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c37b-112">Requirements</span></span>

<span data-ttu-id="2c37b-113">**어셈블리**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="2c37b-113">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="2c37b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c37b-114">See also</span></span>

- [<span data-ttu-id="2c37b-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2c37b-115">Authenticode</span></span>](index.md)
