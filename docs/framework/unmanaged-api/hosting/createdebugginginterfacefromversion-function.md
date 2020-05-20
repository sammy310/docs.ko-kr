---
title: CreateDebuggingInterfaceFromVersion 함수
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: 0e1395229b67c4054df62935375a4136edf63078
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616491"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="c8e76-102">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="c8e76-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="c8e76-103">지정 된 버전 정보를 기반으로 [ICorDebug](../debugging/icordebug-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-103">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="c8e76-104">이 함수는 .NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="c8e76-105">대신 CLR (공용 언어 런타임) 2.0에 대 한 인터페이스를 가져오려면 [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 메서드를 사용 하 고 클래스 식별자 CLSID_CLRDebuggingLegacy 및 인터페이스 식별자 IID_ICorDebug를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="c8e76-106">CLR 4 이상에 대 한 인터페이스를 가져오려면 [Clrcreateinstance](clrcreateinstance-function.md) 함수를 호출 하 고 클래스 식별자 CLSID_CLRDebugging 및 인터페이스 식별자 IID_ICLRDebugging를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e76-107">구문</span><span class="sxs-lookup"><span data-stu-id="c8e76-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8e76-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8e76-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="c8e76-109">진행 디버거에 필요한의 버전입니다 `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="c8e76-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="c8e76-110">올바른 값은 [Cordebuginterfaceversion](../debugging/cordebuginterfaceversion-enumeration.md) 열거형을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e76-110">See the [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="c8e76-111">진행 디버그할 응용 프로그램 또는 프로세스와 연결 된 공용 언어 런타임 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="c8e76-112">이 값을 검색 하는 방법에 대 한 자세한 내용은 [Getversionfromprocess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 또는 [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e76-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="c8e76-113">제한이 개체에 대 한 포인터를 수신 하는 위치입니다 `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="c8e76-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8e76-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="c8e76-114">Return Value</span></span>  
 <span data-ttu-id="c8e76-115">이 메서드는 다음 값 외에도 Winerror.h 파일에 정의 된 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="c8e76-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="c8e76-116">Return code</span></span>|<span data-ttu-id="c8e76-117">설명</span><span class="sxs-lookup"><span data-stu-id="c8e76-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c8e76-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8e76-118">S_OK</span></span>|<span data-ttu-id="c8e76-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="c8e76-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c8e76-120">E_INVALIDARG</span></span>|<span data-ttu-id="c8e76-121">`szDebuggeeVersion`또는 `ppCordb` 이 null 이거나 버전 문자열이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8e76-122">설명</span><span class="sxs-lookup"><span data-stu-id="c8e76-122">Remarks</span></span>  
 <span data-ttu-id="c8e76-123">`szDebuggeeVersion`매개 변수는 해당 버전의 mscordbi.dll에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8e76-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8e76-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8e76-124">Requirements</span></span>  
 <span data-ttu-id="c8e76-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e76-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8e76-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c8e76-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8e76-127">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c8e76-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8e76-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e76-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e76-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8e76-129">See also</span></span>

- [<span data-ttu-id="c8e76-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="c8e76-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
