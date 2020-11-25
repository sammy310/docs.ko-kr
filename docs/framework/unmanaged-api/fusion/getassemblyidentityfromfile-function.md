---
title: GetAssemblyIdentityFromFile 함수
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724483"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="b1976-102">GetAssemblyIdentityFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="b1976-102">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="b1976-103">`IUnknown`어셈블리에서 지정 된 파일 경로의 지정 된을 사용 하 여 개체에 대 한 포인터를 가져옵니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="b1976-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1976-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1976-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1976-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1976-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="b1976-106">진행 요청 된 어셈블리에 대 한 올바른 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b1976-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="b1976-107">진행 `IID` 반환할 인터페이스의입니다.</span><span class="sxs-lookup"><span data-stu-id="b1976-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="b1976-108">제한이 반환 된 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1976-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1976-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1976-109">Requirements</span></span>  

 <span data-ttu-id="b1976-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1976-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1976-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b1976-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b1976-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1976-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1976-113">참조</span><span class="sxs-lookup"><span data-stu-id="b1976-113">See also</span></span>

- [<span data-ttu-id="b1976-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="b1976-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="b1976-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b1976-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
