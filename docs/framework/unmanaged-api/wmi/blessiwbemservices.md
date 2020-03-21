---
title: BlessIWbemServices 함수(관리되지 않는 API 참조)
description: BlessIWbemServices 함수는 사용자 자격 증명이 IWbemServices 클래스에 대한 액세스를 허용하는지 여부를 나타냅니다.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4b15af840cc00b3ec261604db4f3625c6b975d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176866"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="1a1c4-103">BlessIWbemServices 함수</span><span class="sxs-lookup"><span data-stu-id="1a1c4-103">BlessIWbemServices function</span></span>
<span data-ttu-id="1a1c4-104">사용자 자격 증명이 지정된 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 클래스에 대한 액세스를 허용하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1a1c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="1a1c4-105">Syntax</span></span>  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="1a1c4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a1c4-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="1a1c4-107">【인】 권한이 필요한 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="1a1c4-108">【인】 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="1a1c4-109">【인】 와 연결된 `strUser`암호입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="1a1c4-110">【인】 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-110">[in] The domain name of the user.</span></span> <span data-ttu-id="1a1c4-111">자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="1a1c4-112">【인】 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="1a1c4-113">【인】 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="1a1c4-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="1a1c4-114">Return value</span></span>

<span data-ttu-id="1a1c4-115">이 함수에서 반환되는 다음 값은 *WinError.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1a1c4-116">지속적임</span><span class="sxs-lookup"><span data-stu-id="1a1c4-116">Constant</span></span>  |<span data-ttu-id="1a1c4-117">값</span><span class="sxs-lookup"><span data-stu-id="1a1c4-117">Value</span></span>  |<span data-ttu-id="1a1c4-118">Description</span><span class="sxs-lookup"><span data-stu-id="1a1c4-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="1a1c4-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="1a1c4-119">0x80070057</span></span> | <span data-ttu-id="1a1c4-120">하나 이상의 인수가 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="1a1c4-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="1a1c4-121">0x80004003</span></span> | <span data-ttu-id="1a1c4-122">`pIWbemServices`은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="1a1c4-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="1a1c4-123">0x80000008</span></span> | <span data-ttu-id="1a1c4-124">알 수 없는 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="1a1c4-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="1a1c4-125">0x80000002</span></span> | <span data-ttu-id="1a1c4-126">작업을 수행하기 위해 메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="1a1c4-127">0</span><span class="sxs-lookup"><span data-stu-id="1a1c4-127">0</span></span> | <span data-ttu-id="1a1c4-128">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="1a1c4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a1c4-129">Requirements</span></span>  

 <span data-ttu-id="1a1c4-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a1c4-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a1c4-131">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1a1c4-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1a1c4-132">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1a1c4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a1c4-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a1c4-133">See also</span></span>

- [<span data-ttu-id="1a1c4-134">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1a1c4-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
