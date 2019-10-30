---
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
ms.openlocfilehash: f089769f854bad5d3e572e0307734e06e72ca89c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108561"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="5ad1d-102">CreateInstallReferenceEnum 함수</span><span class="sxs-lookup"><span data-stu-id="5ad1d-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="5ad1d-103">지정 된 어셈블리에 대 한 응용 프로그램 참조 목록을 나타내는 [Iinstallreferenceenum](iinstallreferenceenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ad1d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ad1d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ad1d-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="5ad1d-106">제한이 반환 된 `IInstallReferenceEnum` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="5ad1d-107">진행 참조를 열거 하는 데 사용할 어셈블리를 식별 하는 [IAssemblyName](iassemblyname-interface.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5ad1d-108">진행 열거자의 동작에 영향을 주는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="5ad1d-109">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="5ad1d-110">`pvReserved`은 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ad1d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ad1d-111">Requirements</span></span>  
 <span data-ttu-id="5ad1d-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad1d-113">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5ad1d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5ad1d-114">**라이브러리:** Fusion 및 Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="5ad1d-115">Mscorwks.dll 대신 Fusion을 사용 하 여 올바른 버전의 .NET Framework를 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="5ad1d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ad1d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad1d-117">참조</span><span class="sxs-lookup"><span data-stu-id="5ad1d-117">See also</span></span>

- [<span data-ttu-id="5ad1d-118">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ad1d-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="5ad1d-119">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ad1d-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="5ad1d-120">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5ad1d-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
