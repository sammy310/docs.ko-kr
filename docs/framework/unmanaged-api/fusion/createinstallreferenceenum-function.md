---
description: '자세한 정보: CreateInstallReferenceEnum 함수'
title: CreateInstallReferenceEnum 함수
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: cc7551707cb46bcf0c475a0095684dbc790836e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761150"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="cd1a6-103">CreateInstallReferenceEnum 함수</span><span class="sxs-lookup"><span data-stu-id="cd1a6-103">CreateInstallReferenceEnum Function</span></span>

<span data-ttu-id="cd1a6-104">지정 된 어셈블리에 대 한 응용 프로그램 참조 목록을 나타내는 [Iinstallreferenceenum](iinstallreferenceenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-104">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd1a6-105">구문</span><span class="sxs-lookup"><span data-stu-id="cd1a6-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd1a6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd1a6-106">Parameters</span></span>  

 `ppRefEnum`  
 <span data-ttu-id="cd1a6-107">제한이 반환 된 `IInstallReferenceEnum` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-107">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="cd1a6-108">진행 참조를 열거 하는 데 사용할 어셈블리를 식별 하는 [IAssemblyName](iassemblyname-interface.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-108">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cd1a6-109">진행 열거자의 동작에 영향을 주는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-109">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="cd1a6-110">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="cd1a6-111">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd1a6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd1a6-112">Requirements</span></span>  

 <span data-ttu-id="cd1a6-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd1a6-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cd1a6-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cd1a6-115">**라이브러리:** Fusion.dll 및 Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-115">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="cd1a6-116">Mscorwks.dll 대신 Fusion.dll를 사용 하 여 올바른 버전의 .NET Framework를 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1a6-116">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cd1a6-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd1a6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1a6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd1a6-118">See also</span></span>

- [<span data-ttu-id="cd1a6-119">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd1a6-119">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="cd1a6-120">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd1a6-120">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="cd1a6-121">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="cd1a6-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
