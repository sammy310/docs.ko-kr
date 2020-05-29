---
title: Basic Serialization 기술 샘플
description: 이 샘플에서는 메모리의 개체 그래프를 스트림으로 직렬화하는 CLR 기능을 보여 줍니다. 이 샘플에서는 SoapFormatter 또는 BinaryFormatter를 사용할 수 있습니다.
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: fcbf790c3b3d48a0aeb27fd1ef6f75dcd7609ae0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378435"
---
# <a name="basic-serialization-technology-sample"></a><span data-ttu-id="4eacf-104">Basic Serialization 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="4eacf-104">Basic Serialization Technology Sample</span></span>

[<span data-ttu-id="4eacf-105">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="4eacf-105">Download sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

<span data-ttu-id="4eacf-106">이 샘플에서는 메모리에서 개체 그래프를 스트림으로 serialize하는 공용 언어 런타임의 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-106">This sample demonstrates the common language runtime's ability to serialize an object graph in memory to a stream.</span></span> <span data-ttu-id="4eacf-107">이 샘플에서는 serialization을 위해 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>를 사용할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="4eacf-107">This sample can use either the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> or the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> for serialization.</span></span> <span data-ttu-id="4eacf-108">데이터가 채워진 연결된 목록을 파일 스트림으로 직렬화하거나 파일 스트림에서 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-108">A linked list, filled with data, is serialized or deserialized to or from a file stream.</span></span> <span data-ttu-id="4eacf-109">두 경우 모두 결과를 확인할 수 있도록 목록이 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-109">In either case the list is displayed so that you can see the results.</span></span> <span data-ttu-id="4eacf-110">연결된 목록은 이 샘플에서 정의한 형식인 `LinkedList` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-110">The linked list is of type `LinkedList`, a type defined by this sample.</span></span>

<span data-ttu-id="4eacf-111">serialization에 대한 자세한 내용은 build.proj 파일 및 소스 코드의 주석을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4eacf-111">Review comments in the source code and build.proj files for more information on serialization.</span></span>

### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="4eacf-112">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="4eacf-112">To build the sample using the Command Prompt</span></span>

1. <span data-ttu-id="4eacf-113">명령 프롬프트를 사용하여 Technologies\Serialization\Runtime Serialization\Basic 디렉터리 아래의 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-113">Navigate to one of the language-specific subdirectories under the Technologies\Serialization\Runtime Serialization\Basic directory, using the command prompt.</span></span>

2. <span data-ttu-id="4eacf-114">선택한 프로그래밍 언어에 따라 **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** 또는 **msbuild SerializationVB.sln**을 명령줄에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-114">Type **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** or **msbuild SerializationVB.sln**, depending on your choice of programming language, at the command line.</span></span>

### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="4eacf-115">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="4eacf-115">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="4eacf-116">파일 탐색기를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-116">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>

2. <span data-ttu-id="4eacf-117">선택한 프로그래밍 언어에 따라 RemotingIPCCS.sln, RemotingIPCJSL.sln 또는 RemotingIPCVB.sln 파일의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-117">Double-click the icon for the SerializationCS.sln, SerializationJSL.sln or SerializationVB.sln file, depending on your choice of programming language, to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="4eacf-118">**빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-118">In the **Build** menu, select **Build Solution**.</span></span>

 <span data-ttu-id="4eacf-119">샘플 애플리케이션이 기본 \bin 또는 \bin\Debug 하위 디렉터리에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-119">The sample application will be built in the default \bin or \bin\Debug subdirectory.</span></span>

### <a name="to-run-the-sample"></a><span data-ttu-id="4eacf-120">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4eacf-120">To run the sample</span></span>

1. <span data-ttu-id="4eacf-121">빌드된 실행 파일이 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-121">Navigate to the directory containing the built executable.</span></span>

2. <span data-ttu-id="4eacf-122">원하는 매개 변수 값과 함께 **Serialization.exe**를 명령줄에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-122">Type **Serialization.exe**, along with the parameter values you desire, at the command line.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4eacf-123">이 샘플은 콘솔 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-123">This sample builds a console application.</span></span> <span data-ttu-id="4eacf-124">출력을 보려면 명령 프롬프트를 사용하여 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-124">You must launch it using the command prompt in order to view its output.</span></span>

## <a name="remarks"></a><span data-ttu-id="4eacf-125">설명</span><span class="sxs-lookup"><span data-stu-id="4eacf-125">Remarks</span></span>

<span data-ttu-id="4eacf-126">이 샘플 애플리케이션에서는 실행할 테스트를 지정하는 명령줄 매개 변수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-126">The sample application accepts command line parameters indicating which test you would like to execute.</span></span> <span data-ttu-id="4eacf-127">노드가 10개인 목록을 SOAP 포맷터를 사용하여 **Test.xml** 파일로 직렬화하려면 **sx Test.xml 10** 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-127">To serialize a 10-node list to a file named **Test.xml** using the SOAP formatter, use the parameters **sx Test.xml 10**.</span></span>

<span data-ttu-id="4eacf-128">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-128">For Example:</span></span>

```console
Serialize.exe -sx Test.xml 10
```

<span data-ttu-id="4eacf-129">이전 샘플의 **Test.xml** 파일을 역직렬화하려면 매개 변수로 **dx Test.xml**을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-129">To deserialize the **Test.xml** file from the previous example, use the parameters **dx Test.xml**.</span></span>

<span data-ttu-id="4eacf-130">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-130">For Example:</span></span>

```console
Serialize.exe -dx Test.xml
```

<span data-ttu-id="4eacf-131">위의 두 예제에서 명령줄 스위치에 있는 "x"는 XML SOAP serialization을 사용하도록 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-131">In the two examples above, the "x" in the command line switch indicates that you want XML SOAP serialization.</span></span> <span data-ttu-id="4eacf-132">이진 serialization을 사용하려면 대신 "b"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-132">You can use "b" in its place to use binary serialization.</span></span> <span data-ttu-id="4eacf-133">매우 많은 노드를 serialize하는 경우에는 콘솔 출력을 파일로 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-133">If you wish to try serialization with a very large number of nodes, you might want to redirect the console output to a file.</span></span>

<span data-ttu-id="4eacf-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-134">For Example:</span></span>

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

<span data-ttu-id="4eacf-135">이 샘플에 사용된 클래스 및 기술이 아래에 간략하게 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-135">The following bullets briefly describe the classes and technologies used by this sample.</span></span>

- <span data-ttu-id="4eacf-136">런타임 serialization</span><span class="sxs-lookup"><span data-stu-id="4eacf-136">Runtime Serialization</span></span>

  - <span data-ttu-id="4eacf-137"><xref:System.Runtime.Serialization.IFormatter> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 개체를 참조하기 위해 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-137"><xref:System.Runtime.Serialization.IFormatter> Used to refer to either a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> object.</span></span>

  - <span data-ttu-id="4eacf-138">연결된 목록을 스트림에 이진 형식으로 serialize하기 위해 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Used to serialize a linked list to a stream in a binary format.</span></span> <span data-ttu-id="4eacf-139">이진 포맷터는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 형식에서만 인식할 수 있는 형식을 사용하지만,</span><span class="sxs-lookup"><span data-stu-id="4eacf-139">The binary formatter uses a format that only the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type understands.</span></span> <span data-ttu-id="4eacf-140">데이터가 간결해지는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-140">However, the data is concise.</span></span>

  - <span data-ttu-id="4eacf-141">연결된 목록을 SOAP 형식의 스트림으로 직렬화하는 데 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-141"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Used to serialize a linked list to a stream in the SOAP format.</span></span> <span data-ttu-id="4eacf-142">SOAP는 표준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-142">SOAP is a standard format.</span></span>

- <span data-ttu-id="4eacf-143">스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="4eacf-143">Stream I/O</span></span>

  - <span data-ttu-id="4eacf-144">직렬화 및 역직렬화를 위해 <xref:System.IO.Stream>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-144"><xref:System.IO.Stream> Used to serialize and deserialize.</span></span> <span data-ttu-id="4eacf-145">이 샘플에서 사용되는 특정 스트림 형식은 <xref:System.IO.FileStream> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-145">The specific stream type used in this sample is the <xref:System.IO.FileStream> type.</span></span> <span data-ttu-id="4eacf-146">그러나 serialization에는 <xref:System.IO.Stream>에서 파생되는 모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-146">However, serialization can be used with any type derived from <xref:System.IO.Stream>.</span></span>

  - <span data-ttu-id="4eacf-147">디스크에 파일을 생성하고 디스크의 파일을 읽기 위한 <xref:System.IO.File> 개체를 만들기 위해 <xref:System.IO.FileStream>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-147"><xref:System.IO.File> Used to create <xref:System.IO.FileStream> objects for reading and creating files on disk.</span></span>

  - <span data-ttu-id="4eacf-148">연결된 목록을 직렬화 및 역직렬화하기 위해 <xref:System.IO.FileStream>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eacf-148"><xref:System.IO.FileStream> Used to serialize and deserialize linked lists.</span></span>

## <a name="see-also"></a><span data-ttu-id="4eacf-149">참조</span><span class="sxs-lookup"><span data-stu-id="4eacf-149">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="4eacf-150">기본 serialization</span><span class="sxs-lookup"><span data-stu-id="4eacf-150">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="4eacf-151">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="4eacf-151">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="4eacf-152">특성을 사용하여 XML serialization 제어</span><span class="sxs-lookup"><span data-stu-id="4eacf-152">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="4eacf-153">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="4eacf-153">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="4eacf-154">serialization</span><span class="sxs-lookup"><span data-stu-id="4eacf-154">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="4eacf-155">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="4eacf-155">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
