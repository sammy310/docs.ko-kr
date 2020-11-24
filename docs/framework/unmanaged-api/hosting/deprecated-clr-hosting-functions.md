---
title: 사용되지 않는 CLR 호스팅 함수
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 9e19502672973f292991b72c7ea9b4fdc17f5707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673126"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="7bb41-102">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-102">Deprecated CLR Hosting Functions</span></span>

<span data-ttu-id="7bb41-103">이 섹션에서는 이전 버전의 호스팅 API가 사용 하는 관리 되지 않는 전역 정적 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="7bb41-104">.NET Framework에만 사용 되는 인프라 함수 (함수)를 제외 하 고 `_Cor*` , 이러한 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="7bb41-105">활성화 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-105">Activation functions</span></span>  

 [<span data-ttu-id="7bb41-106">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="7bb41-107">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-107">Deprecated.</span></span> <span data-ttu-id="7bb41-108">지정 된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="7bb41-109">CoInitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="7bb41-110">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-110">Obsolete.</span></span> <span data-ttu-id="7bb41-111">CLR (공용 언어 런타임)을 초기화 하려면 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="7bb41-112">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="7bb41-113">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-113">Deprecated.</span></span> <span data-ttu-id="7bb41-114">CLR 실행 엔진이 프로세스로 로드 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="7bb41-115">대신 [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="7bb41-116">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="7bb41-117">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-117">Deprecated.</span></span> <span data-ttu-id="7bb41-118">XML 파일에 저장 된 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="7bb41-119">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="7bb41-120">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-120">Deprecated.</span></span> <span data-ttu-id="7bb41-121">관리 되지 않는 호스트에서 CLR을 프로세스로 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="7bb41-122">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="7bb41-123">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-123">Deprecated.</span></span> <span data-ttu-id="7bb41-124">XML 파일에서 읽은 버전 정보를 사용 하 여 CLR을 프로세스로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="7bb41-125">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="7bb41-126">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-126">Deprecated.</span></span> <span data-ttu-id="7bb41-127">관리 되지 않는 호스트에서 CLR을 프로세스로 로드할 수 있도록 하 고, CLR의 동작을 지정 하는 플래그를 설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="7bb41-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="7bb41-129">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-129">Deprecated.</span></span> <span data-ttu-id="7bb41-130">호스트에서 지정 된 버전의 CLR을 프로세스로 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="7bb41-131">GetCORRequiredVersion 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="7bb41-132">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-132">Deprecated.</span></span> <span data-ttu-id="7bb41-133">필요한 CLR 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="7bb41-134">GetCORSystemDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="7bb41-135">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-135">Deprecated.</span></span> <span data-ttu-id="7bb41-136">프로세스에 로드 된 CLR의 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="7bb41-137">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="7bb41-138">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-138">Deprecated.</span></span> <span data-ttu-id="7bb41-139">최신 버전의 CLR에서 내보낸 지정 된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="7bb41-140">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="7bb41-141">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-141">Deprecated.</span></span> <span data-ttu-id="7bb41-142">응용 프로그램에서 요청한 CLR에 대 한 버전 및 디렉터리 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="7bb41-143">CLR 버전 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-143">CLR version functions</span></span>  

 <span data-ttu-id="7bb41-144">이 단원의 함수는 CLR 버전을 반환 합니다. CLR을 활성화 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="7bb41-145">GetCORVersion 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="7bb41-146">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-146">Deprecated.</span></span> <span data-ttu-id="7bb41-147">현재 프로세스에서 실행 중인 CLR의 버전 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="7bb41-148">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="7bb41-149">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-149">Deprecated.</span></span> <span data-ttu-id="7bb41-150">지정 된 버퍼를 사용 하 여 지정 된 파일의 CLR 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="7bb41-151">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="7bb41-152">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-152">Deprecated.</span></span> <span data-ttu-id="7bb41-153">지정 된 응용 프로그램에서 요청한 CLR의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="7bb41-154">해당 버전이 설치 되지 않은 경우는 요청 된 버전 보다 먼저 설치 된 최신 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="7bb41-155">GetRequestedRuntimeVersionForCLSID 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="7bb41-156">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-156">Deprecated.</span></span> <span data-ttu-id="7bb41-157">지정 된 CLSID를 사용 하 여 클래스에 대 한 적절 한 CLR 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="7bb41-158">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="7bb41-159">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-159">Deprecated.</span></span> <span data-ttu-id="7bb41-160">지정 된 프로세스 핸들과 연결 된 CLR의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="7bb41-161">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="7bb41-162">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-162">Deprecated.</span></span> <span data-ttu-id="7bb41-163">호스트에서 CLR을 명시적으로 초기화 하기 전에 프로세스 내에서 사용 되는 CLR 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="7bb41-164">호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-164">Hosting functions</span></span>  

 [<span data-ttu-id="7bb41-165">CallFunctionShim 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="7bb41-166">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-166">Deprecated.</span></span> <span data-ttu-id="7bb41-167">지정 된 라이브러리에서 지정 된 이름 및 매개 변수를 가진 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="7bb41-168">CoEEShutDownCOM 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="7bb41-169">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-169">Deprecated.</span></span> <span data-ttu-id="7bb41-170">프로세스에서 COM 어셈블리를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="7bb41-171">CorExitProcess 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="7bb41-172">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-172">Deprecated.</span></span> <span data-ttu-id="7bb41-173">현재 관리 되지 않는 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="7bb41-174">CorLaunchApplication 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="7bb41-175">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-175">Deprecated.</span></span> <span data-ttu-id="7bb41-176">지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="7bb41-177">CorMarkThreadInThreadPool 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="7bb41-178">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-178">Deprecated.</span></span> <span data-ttu-id="7bb41-179">관리 코드 실행을 위해 현재 실행 중인 스레드 풀 스레드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="7bb41-180">.NET Framework 버전 2.0부터이 함수는 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="7bb41-181">필요 하지 않으며 코드에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="7bb41-182">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="7bb41-183">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-183">Obsolete.</span></span> <span data-ttu-id="7bb41-184">CLR은 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="7bb41-185">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="7bb41-186">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="7bb41-187">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="7bb41-188">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-188">Deprecated.</span></span> <span data-ttu-id="7bb41-189">지정 된 버전 정보를 기반으로 [ICorDebug](../debugging/icordebug-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="7bb41-190">CreateICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="7bb41-191">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-191">Deprecated.</span></span> <span data-ttu-id="7bb41-192">[ICeeFileGen](iceefilegen-class.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="7bb41-193">DestroyICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="7bb41-194">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-194">Deprecated.</span></span> <span data-ttu-id="7bb41-195">[ICeeFileGen](iceefilegen-class.md) 개체를 소멸 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="7bb41-196">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="7bb41-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="7bb41-197">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-197">Deprecated.</span></span> <span data-ttu-id="7bb41-198">관리 코드를 실행 하기 위해 CLR이 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="7bb41-199">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="7bb41-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="7bb41-200">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-200">Deprecated.</span></span> <span data-ttu-id="7bb41-201">는 초기화가 시작 되거나 완료 되었음을 호스트에 알리기 위해 CLR에서 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="7bb41-202">GetCLRIdentityManager 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="7bb41-203">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-203">Deprecated.</span></span> <span data-ttu-id="7bb41-204">CLR에서 id를 관리할 수 있도록 하는 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="7bb41-205">LoadLibraryShim 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="7bb41-206">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-206">Deprecated.</span></span> <span data-ttu-id="7bb41-207">지정 된 버전의 .NET Framework DLL을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="7bb41-208">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="7bb41-209">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-209">Deprecated.</span></span> <span data-ttu-id="7bb41-210">현재 스레드의 기본 문화권을 사용 하 여 HRESULT 값을 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="7bb41-211">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="7bb41-212">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-212">Deprecated.</span></span> <span data-ttu-id="7bb41-213">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="7bb41-214">LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="7bb41-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="7bb41-215">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-215">Deprecated.</span></span> <span data-ttu-id="7bb41-216">장치에 대해 겹치는 (즉, 비동기) i/o가 완료 되었을 때 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="7bb41-217">LPTHREAD_START_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="7bb41-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="7bb41-218">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-218">Deprecated.</span></span> <span data-ttu-id="7bb41-219">스레드가 실행을 시작 했음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="7bb41-220">RunDll32ShimW 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="7bb41-221">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-221">Deprecated.</span></span> <span data-ttu-id="7bb41-222">지정된 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="7bb41-223">WAITORTIMERCALLBACK 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="7bb41-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="7bb41-224">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-224">Deprecated.</span></span> <span data-ttu-id="7bb41-225">대기 핸들이 신호를 받았거나 시간이 초과 되었음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="7bb41-226">인프라 기능</span><span class="sxs-lookup"><span data-stu-id="7bb41-226">Infrastructure functions</span></span>  

 <span data-ttu-id="7bb41-227">이 섹션의 함수는 .NET Framework 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="7bb41-228">_CorDllMain 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="7bb41-229">CLR을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="7bb41-230">_CorExeMain 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="7bb41-231">CLR을 초기화 하 고, 실행 가능한 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="7bb41-232">_CorExeMain2 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="7bb41-233">지정 된 메모리 매핑된 코드에서 진입점을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="7bb41-234">이 함수는 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="7bb41-235">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="7bb41-236">관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="7bb41-237">_CorValidateImage 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="7bb41-238">관리 되는 모듈 이미지의 유효성을 검사 하 고, 운영 체제 로더가 로드 된 후이를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7bb41-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb41-239">참조</span><span class="sxs-lookup"><span data-stu-id="7bb41-239">See also</span></span>

- [<span data-ttu-id="7bb41-240">.NET Framework 4 호스팅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7bb41-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
