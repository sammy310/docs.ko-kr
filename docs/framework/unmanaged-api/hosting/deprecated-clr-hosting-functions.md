---
title: 사용되지 않는 CLR 호스팅 함수
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504370"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="31c3b-102">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="31c3b-103">이 섹션에서는 이전 버전의 호스팅 API가 사용 하는 관리 되지 않는 전역 정적 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="31c3b-104">.NET Framework에만 사용 되는 인프라 함수 (함수)를 제외 하 고 `_Cor*` , 이러한 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="31c3b-105">활성화 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-105">Activation functions</span></span>  
 [<span data-ttu-id="31c3b-106">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="31c3b-107">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-107">Deprecated.</span></span> <span data-ttu-id="31c3b-108">지정 된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="31c3b-109">CoInitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="31c3b-110">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-110">Obsolete.</span></span> <span data-ttu-id="31c3b-111">CLR (공용 언어 런타임)을 초기화 하려면 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="31c3b-112">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="31c3b-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-113">Deprecated.</span></span> <span data-ttu-id="31c3b-114">CLR 실행 엔진이 프로세스로 로드 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="31c3b-115">대신 [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="31c3b-116">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="31c3b-117">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-117">Deprecated.</span></span> <span data-ttu-id="31c3b-118">XML 파일에 저장 된 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="31c3b-119">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="31c3b-120">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-120">Deprecated.</span></span> <span data-ttu-id="31c3b-121">관리 되지 않는 호스트에서 CLR을 프로세스로 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="31c3b-122">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="31c3b-123">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-123">Deprecated.</span></span> <span data-ttu-id="31c3b-124">XML 파일에서 읽은 버전 정보를 사용 하 여 CLR을 프로세스로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="31c3b-125">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="31c3b-126">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-126">Deprecated.</span></span> <span data-ttu-id="31c3b-127">관리 되지 않는 호스트에서 CLR을 프로세스로 로드할 수 있도록 하 고, CLR의 동작을 지정 하는 플래그를 설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="31c3b-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="31c3b-129">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-129">Deprecated.</span></span> <span data-ttu-id="31c3b-130">호스트에서 지정 된 버전의 CLR을 프로세스로 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="31c3b-131">GetCORRequiredVersion 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="31c3b-132">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-132">Deprecated.</span></span> <span data-ttu-id="31c3b-133">필요한 CLR 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="31c3b-134">GetCORSystemDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="31c3b-135">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-135">Deprecated.</span></span> <span data-ttu-id="31c3b-136">프로세스에 로드 된 CLR의 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="31c3b-137">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="31c3b-138">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-138">Deprecated.</span></span> <span data-ttu-id="31c3b-139">최신 버전의 CLR에서 내보낸 지정 된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="31c3b-140">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="31c3b-141">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-141">Deprecated.</span></span> <span data-ttu-id="31c3b-142">응용 프로그램에서 요청한 CLR에 대 한 버전 및 디렉터리 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="31c3b-143">CLR 버전 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-143">CLR version functions</span></span>  
 <span data-ttu-id="31c3b-144">이 단원의 함수는 CLR 버전을 반환 합니다. CLR을 활성화 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="31c3b-145">GetCORVersion 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="31c3b-146">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-146">Deprecated.</span></span> <span data-ttu-id="31c3b-147">현재 프로세스에서 실행 중인 CLR의 버전 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="31c3b-148">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="31c3b-149">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-149">Deprecated.</span></span> <span data-ttu-id="31c3b-150">지정 된 버퍼를 사용 하 여 지정 된 파일의 CLR 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="31c3b-151">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="31c3b-152">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-152">Deprecated.</span></span> <span data-ttu-id="31c3b-153">지정 된 응용 프로그램에서 요청한 CLR의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="31c3b-154">해당 버전이 설치 되지 않은 경우는 요청 된 버전 보다 먼저 설치 된 최신 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="31c3b-155">GetRequestedRuntimeVersionForCLSID 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="31c3b-156">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-156">Deprecated.</span></span> <span data-ttu-id="31c3b-157">지정 된 CLSID를 사용 하 여 클래스에 대 한 적절 한 CLR 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="31c3b-158">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="31c3b-159">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-159">Deprecated.</span></span> <span data-ttu-id="31c3b-160">지정 된 프로세스 핸들과 연결 된 CLR의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="31c3b-161">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="31c3b-162">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-162">Deprecated.</span></span> <span data-ttu-id="31c3b-163">호스트에서 CLR을 명시적으로 초기화 하기 전에 프로세스 내에서 사용 되는 CLR 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="31c3b-164">호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-164">Hosting functions</span></span>  
 [<span data-ttu-id="31c3b-165">CallFunctionShim 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="31c3b-166">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-166">Deprecated.</span></span> <span data-ttu-id="31c3b-167">지정 된 라이브러리에서 지정 된 이름 및 매개 변수를 가진 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="31c3b-168">CoEEShutDownCOM 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="31c3b-169">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-169">Deprecated.</span></span> <span data-ttu-id="31c3b-170">프로세스에서 COM 어셈블리를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="31c3b-171">CorExitProcess 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="31c3b-172">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-172">Deprecated.</span></span> <span data-ttu-id="31c3b-173">현재 관리 되지 않는 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="31c3b-174">CorLaunchApplication 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="31c3b-175">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-175">Deprecated.</span></span> <span data-ttu-id="31c3b-176">지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="31c3b-177">CorMarkThreadInThreadPool 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="31c3b-178">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-178">Deprecated.</span></span> <span data-ttu-id="31c3b-179">관리 코드 실행을 위해 현재 실행 중인 스레드 풀 스레드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="31c3b-180">.NET Framework 버전 2.0부터이 함수는 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="31c3b-181">필요 하지 않으며 코드에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="31c3b-182">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="31c3b-183">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-183">Obsolete.</span></span> <span data-ttu-id="31c3b-184">CLR은 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="31c3b-185">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="31c3b-186">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="31c3b-187">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="31c3b-188">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-188">Deprecated.</span></span> <span data-ttu-id="31c3b-189">지정 된 버전 정보를 기반으로 [ICorDebug](../debugging/icordebug-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="31c3b-190">CreateICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="31c3b-191">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-191">Deprecated.</span></span> <span data-ttu-id="31c3b-192">[ICeeFileGen](iceefilegen-class.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="31c3b-193">DestroyICeeFileGen 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="31c3b-194">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-194">Deprecated.</span></span> <span data-ttu-id="31c3b-195">[ICeeFileGen](iceefilegen-class.md) 개체를 소멸 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="31c3b-196">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="31c3b-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="31c3b-197">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-197">Deprecated.</span></span> <span data-ttu-id="31c3b-198">관리 코드를 실행 하기 위해 CLR이 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="31c3b-199">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="31c3b-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="31c3b-200">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-200">Deprecated.</span></span> <span data-ttu-id="31c3b-201">는 초기화가 시작 되거나 완료 되었음을 호스트에 알리기 위해 CLR에서 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="31c3b-202">GetCLRIdentityManager 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="31c3b-203">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-203">Deprecated.</span></span> <span data-ttu-id="31c3b-204">CLR에서 id를 관리할 수 있도록 하는 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="31c3b-205">LoadLibraryShim 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="31c3b-206">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-206">Deprecated.</span></span> <span data-ttu-id="31c3b-207">지정 된 버전의 .NET Framework DLL을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="31c3b-208">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="31c3b-209">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-209">Deprecated.</span></span> <span data-ttu-id="31c3b-210">현재 스레드의 기본 문화권을 사용 하 여 HRESULT 값을 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="31c3b-211">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="31c3b-212">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-212">Deprecated.</span></span> <span data-ttu-id="31c3b-213">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="31c3b-214">LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="31c3b-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="31c3b-215">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-215">Deprecated.</span></span> <span data-ttu-id="31c3b-216">장치에 대해 겹치는 (즉, 비동기) i/o가 완료 되었을 때 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="31c3b-217">LPTHREAD_START_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="31c3b-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="31c3b-218">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-218">Deprecated.</span></span> <span data-ttu-id="31c3b-219">스레드가 실행을 시작 했음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="31c3b-220">RunDll32ShimW 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="31c3b-221">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-221">Deprecated.</span></span> <span data-ttu-id="31c3b-222">지정된 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="31c3b-223">WAITORTIMERCALLBACK 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="31c3b-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="31c3b-224">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-224">Deprecated.</span></span> <span data-ttu-id="31c3b-225">대기 핸들이 신호를 받았거나 시간이 초과 되었음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="31c3b-226">인프라 기능</span><span class="sxs-lookup"><span data-stu-id="31c3b-226">Infrastructure functions</span></span>  
 <span data-ttu-id="31c3b-227">이 섹션의 함수는 .NET Framework 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="31c3b-228">_CorDllMain 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="31c3b-229">CLR을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="31c3b-230">_CorExeMain 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="31c3b-231">CLR을 초기화 하 고, 실행 가능한 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="31c3b-232">_CorExeMain2 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="31c3b-233">지정 된 메모리 매핑된 코드에서 진입점을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="31c3b-234">이 함수는 운영 체제 로더에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="31c3b-235">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="31c3b-236">관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="31c3b-237">_CorValidateImage 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="31c3b-238">관리 되는 모듈 이미지의 유효성을 검사 하 고, 운영 체제 로더가 로드 된 후이를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31c3b-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c3b-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31c3b-239">See also</span></span>

- [<span data-ttu-id="31c3b-240">.NET Framework 4 호스팅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="31c3b-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
