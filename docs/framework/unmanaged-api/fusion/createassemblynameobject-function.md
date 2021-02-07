---
description: '자세한 정보: CreateAssemblyNameObject 함수'
title: CreateAssemblyNameObject 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 0eaa74bdb37a098ad58b81658229f8c04259b730
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761185"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="cf4fe-103">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="cf4fe-103">CreateAssemblyNameObject Function</span></span>

<span data-ttu-id="cf4fe-104">지정 된 이름을 사용 하 여 어셈블리의 고유 id를 나타내는 [IAssemblyName](iassemblyname-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf4fe-104">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf4fe-105">구문</span><span class="sxs-lookup"><span data-stu-id="cf4fe-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf4fe-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf4fe-106">Parameters</span></span>  

 `ppAssemblyNameObj`  
 <span data-ttu-id="cf4fe-107">제한이 반환 된 `IAssemblyName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4fe-107">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="cf4fe-108">진행 새 인스턴스를 만들 어셈블리의 이름입니다 `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="cf4fe-108">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cf4fe-109">진행 개체 생성자에 전달할 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4fe-109">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="cf4fe-110">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4fe-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="cf4fe-111">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4fe-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf4fe-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf4fe-112">Requirements</span></span>  

 <span data-ttu-id="cf4fe-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf4fe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf4fe-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cf4fe-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cf4fe-115">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4fe-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf4fe-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf4fe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4fe-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf4fe-117">See also</span></span>

- [<span data-ttu-id="cf4fe-118">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf4fe-118">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="cf4fe-119">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="cf4fe-119">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
