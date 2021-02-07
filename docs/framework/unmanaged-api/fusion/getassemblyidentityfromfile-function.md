---
description: '자세히 알아보기: GetAssemblyIdentityFromFile 함수'
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
ms.openlocfilehash: 8832e03182a5652c938404c99115fa8059439d1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761039"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="01811-103">GetAssemblyIdentityFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="01811-103">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="01811-104">`IUnknown`어셈블리에서 지정 된 파일 경로의 지정 된을 사용 하 여 개체에 대 한 포인터를 가져옵니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="01811-104">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01811-105">구문</span><span class="sxs-lookup"><span data-stu-id="01811-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="01811-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01811-106">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="01811-107">진행 요청 된 어셈블리에 대 한 올바른 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="01811-107">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="01811-108">진행 `IID` 반환할 인터페이스의입니다.</span><span class="sxs-lookup"><span data-stu-id="01811-108">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="01811-109">제한이 반환 된 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="01811-109">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01811-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01811-110">Requirements</span></span>  

 <span data-ttu-id="01811-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01811-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01811-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="01811-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="01811-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01811-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01811-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01811-114">See also</span></span>

- [<span data-ttu-id="01811-115">IUnknown</span><span class="sxs-lookup"><span data-stu-id="01811-115">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="01811-116">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="01811-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
