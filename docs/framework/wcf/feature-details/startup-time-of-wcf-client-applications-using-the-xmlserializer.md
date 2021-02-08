---
description: '자세한 정보: 방법: XmlSerializer를 사용 하 여 WCF 클라이언트 응용 프로그램의 시작 시간 개선'
title: '방법: XmlSerializer를 사용하여 WCF 클라이언트 애플리케이션의 시작 시간 향상'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: 8cf46cc35753934e8f4cb3abadc20c912e9efca9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793404"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="9c638-103">방법: XmlSerializer를 사용하여 WCF 클라이언트 애플리케이션의 시작 시간 향상</span><span class="sxs-lookup"><span data-stu-id="9c638-103">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>

<span data-ttu-id="9c638-104"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize할 수 있는 데이터 형식을 사용하는 서비스 및 클라이언트 애플리케이션은 런타임에 해당 데이터 형식에 대한 serialization 코드를 생성하고 컴파일합니다. 이로 인해 시작 시 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-104">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c638-105">미리 생성된 serialization 코드는 서비스가 아닌 클라이언트 애플리케이션에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-105">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="9c638-106">[ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 는 응용 프로그램에 대해 컴파일된 어셈블리에서 필요한 serialization 코드를 생성 하 여 이러한 응용 프로그램의 시작 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-106">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="9c638-107">Svcutil.exe는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize될 수 있는 컴파일된 애플리케이션 어셈블리에서 서비스 계약에 사용하는 모든 데이터 형식에 대한 serialization 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-107">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="9c638-108"><xref:System.Xml.Serialization.XmlSerializer>를 사용하는 서비스 및 작업 계약은 <xref:System.ServiceModel.XmlSerializerFormatAttribute>와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-108">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="9c638-109">XmlSerializer serialization 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="9c638-109">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="9c638-110">서비스 또는 클라이언트 코드를 하나 이상의 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-110">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="9c638-111">SDK 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-111">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="9c638-112">명령 프롬프트에서 다음 형식을 사용하여 Svcutil.exe 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-112">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="9c638-113">`assemblyPath` 인수는 서비스 계약 형식이 포함된 어셈블리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-113">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="9c638-114">Svcutil.exe는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize될 수 있는 컴파일된 애플리케이션 어셈블리에서 서비스 계약에 사용하는 모든 데이터 형식에 대한 serialization 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-114">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="9c638-115">Svcutil.exe는 C# serialization 코드만 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-115">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="9c638-116">각 입력 어셈블리에 대해서 하나의 소스 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-116">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="9c638-117">**/Language** 스위치를 사용 하 여 생성 된 코드의 언어를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-117">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="9c638-118">종속 어셈블리의 경로를 지정 하려면 **/reference** 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-118">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="9c638-119">다음 옵션 중 하나를 사용하여 생성된 serialization 코드를 애플리케이션에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-119">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1. <span data-ttu-id="9c638-120">생성 된 serialization 코드를 이름 [*원본 어셈블리*] .XmlSerializers.dll (예: MyApp.XmlSerializers.dll)를 사용 하 여 별도의 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-120">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="9c638-121">애플리케이션에서 어셈블리를 로드할 수 있어야 하며, 해당 어셈블리는 원본 어셈블리와 동일한 키로 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-121">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="9c638-122">원본 어셈블리를 다시 컴파일하면 serialization 어셈블리도 다시 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-122">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2. <span data-ttu-id="9c638-123">생성된 serialization 코드를 별도의 어셈블리로 컴파일하고 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute>를 사용하는 서비스 계약에 <xref:System.ServiceModel.XmlSerializerFormatAttribute>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-123">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="9c638-124">컴파일된 serialization 어셈블리를 가리키기 위해 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 또는 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-124">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3. <span data-ttu-id="9c638-125">생성된 serialization 코드를 애플리케이션 어셈블리로 컴파일하고 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute>를 사용하는 서비스 계약에 <xref:System.ServiceModel.XmlSerializerFormatAttribute>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-125">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="9c638-126"><xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 또는 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 속성은 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9c638-126">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="9c638-127">기본 serialization 어셈블리가 현재 어셈블리로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-127">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="9c638-128">Visual Studio에서 XmlSerializer serialization 코드를 생성 하려면</span><span class="sxs-lookup"><span data-stu-id="9c638-128">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="9c638-129">Visual Studio에서 WCF 서비스 및 클라이언트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-129">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="9c638-130">그런 다음 서비스 참조를 클라이언트 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-130">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="9c638-131"><xref:System.ServiceModel.XmlSerializerFormatAttribute>클라이언트 앱 프로젝트의 *reference.cs* 파일에서 **serviceReference**  ->  **참조** 의 서비스 계약에를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-131">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="9c638-132">이러한 파일을 보려면 **솔루션 탐색기** 의 모든 파일을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-132">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="9c638-133">클라이언트 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-133">Build the client app.</span></span>  
  
4. <span data-ttu-id="9c638-134">다음 명령을 사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 미리 생성 된 serializer *.cs* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-134">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="9c638-135">AssemblyPath 인수는 WCF 클라이언트 어셈블리에 대 한 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-135">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="9c638-136">예:</span><span class="sxs-lookup"><span data-stu-id="9c638-136">Such as:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="9c638-137">*WCFClient.XmlSerializers.dll .cs* 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-137">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="9c638-138">미리 생성 된 serialization 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-138">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="9c638-139">이전 단계의 예제에 따라 compile 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-139">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="9c638-140">생성 된 *WCFClient.XmlSerializers.dll* 클라이언트 앱과 동일한 디렉터리에 있는지 확인 합니다 .이 경우 *WCFClient.exe* 입니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-140">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="9c638-141">평소와 같이 클라이언트 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-141">Run the client app as usual.</span></span> <span data-ttu-id="9c638-142">미리 생성 된 serialization 어셈블리가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-142">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c638-143">예제</span><span class="sxs-lookup"><span data-stu-id="9c638-143">Example</span></span>  

 <span data-ttu-id="9c638-144">다음 명령은 어셈블리의 모든 서비스 계약이 사용하는 `XmlSerializer` 형식에 대해 serialization 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c638-144">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c638-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c638-145">See also</span></span>

- [<span data-ttu-id="9c638-146">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="9c638-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
