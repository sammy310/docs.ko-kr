---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: abc8a6e4780c8fe50afcf1b04f7e14aeb6452704
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949593"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="ecc1e-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="ecc1e-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="ecc1e-103">현재 열거자와 동일한 상태인 다른 원시 입력 장치 열거자를 만들어 동일한 목록을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc1e-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ecc1e-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecc1e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ecc1e-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="ecc1e-106">[out] 수신 하는 출력 변수의 주소는 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ecc1e-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="ecc1e-107">메서드가 성공 하면이 출력 변수 값 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc1e-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ecc1e-108">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="ecc1e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ecc1e-109">HRESULT: 이 메서드는 표준 반환 값인 E_INVALIDARG, E_OUTOFMEMORY 및 E_UNEXPECTED를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc1e-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc1e-110">설명</span><span class="sxs-lookup"><span data-stu-id="ecc1e-110">Remarks</span></span>  
 <span data-ttu-id="ecc1e-111">이 메서드를 사용 하면 나중에 해당 지점에 반환 하기 위해 한 지점을 열거형 시퀀스에서 기록 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc1e-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="ecc1e-112">호출자는 첫 번째 열거자에서 별도로이 새 열거자를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc1e-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
