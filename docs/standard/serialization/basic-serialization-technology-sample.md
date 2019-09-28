---
title: Basic Serialization 기술 샘플
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: e5dcc9ec7cf6f996c97262b14020552286c530da
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353145"
---
# <a name="basic-serialization-technology-sample"></a><span data-ttu-id="19b30-102">Basic Serialization 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="19b30-102">Basic Serialization Technology Sample</span></span>

[<span data-ttu-id="19b30-103">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="19b30-103">Download sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

<span data-ttu-id="19b30-104">이 샘플에서는 메모리에서 개체 그래프를 스트림으로 serialize하는 공용 언어 런타임의 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-104">This sample demonstrates the common language runtime's ability to serialize an object graph in memory to a stream.</span></span> <span data-ttu-id="19b30-105">이 샘플에서는 serialization을 위해 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>를 사용할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="19b30-105">This sample can use either the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> or the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> for serialization.</span></span> <span data-ttu-id="19b30-106">데이터가 채워진 연결된 목록을 파일 스트림으로 serialize하거나 파일 스트림에서 deserialize합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-106">A linked list, filled with data, is serialized or deserialized to or from a file stream.</span></span> <span data-ttu-id="19b30-107">두 경우 모두 결과를 확인할 수 있도록 목록이 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-107">In either case the list is displayed so that you can see the results.</span></span> <span data-ttu-id="19b30-108">연결된 목록은 이 샘플에서 정의한 형식인 `LinkedList` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-108">The linked list is of type `LinkedList`, a type defined by this sample.</span></span>

<span data-ttu-id="19b30-109">serialization에 대한 자세한 내용은 build.proj 파일 및 소스 코드의 주석을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19b30-109">Review comments in the source code and build.proj files for more information on serialization.</span></span>

### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="19b30-110">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="19b30-110">To build the sample using the Command Prompt</span></span>

1. <span data-ttu-id="19b30-111">명령 프롬프트를 사용하여 Technologies\Serialization\Runtime Serialization\Basic 디렉터리 아래의 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-111">Navigate to one of the language-specific subdirectories under the Technologies\Serialization\Runtime Serialization\Basic directory, using the command prompt.</span></span>

2. <span data-ttu-id="19b30-112">선택한 프로그래밍 언어에 따라 **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** 또는 **msbuild SerializationVB.sln**을 명령줄에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-112">Type **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** or **msbuild SerializationVB.sln**, depending on your choice of programming language, at the command line.</span></span>

### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="19b30-113">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="19b30-113">To build the sample using Visual Studio</span></span>

1. <span data-ttu-id="19b30-114">파일 탐색기를 열고 샘플에 대 한 언어별 하위 디렉터리 중 하나로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-114">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>

2. <span data-ttu-id="19b30-115">선택한 프로그래밍 언어에 따라 RemotingIPCCS.sln, RemotingIPCJSL.sln 또는 RemotingIPCVB.sln 파일의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-115">Double-click the icon for the SerializationCS.sln, SerializationJSL.sln or SerializationVB.sln file, depending on your choice of programming language, to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="19b30-116">**빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-116">In the **Build** menu, select **Build Solution**.</span></span>

 <span data-ttu-id="19b30-117">샘플 애플리케이션이 기본 \bin 또는 \bin\Debug 하위 디렉터리에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-117">The sample application will be built in the default \bin or \bin\Debug subdirectory.</span></span>

### <a name="to-run-the-sample"></a><span data-ttu-id="19b30-118">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="19b30-118">To run the sample</span></span>

1. <span data-ttu-id="19b30-119">빌드된 실행 파일이 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-119">Navigate to the directory containing the built executable.</span></span>

2. <span data-ttu-id="19b30-120">원하는 매개 변수 값과 함께 **Serialization.exe**를 명령줄에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-120">Type **Serialization.exe**, along with the parameter values you desire, at the command line.</span></span>

  > [!NOTE]
  > <span data-ttu-id="19b30-121">이 샘플은 콘솔 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-121">This sample builds a console application.</span></span> <span data-ttu-id="19b30-122">출력을 보려면 명령 프롬프트를 사용하여 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-122">You must launch it using the command prompt in order to view its output.</span></span>

## <a name="remarks"></a><span data-ttu-id="19b30-123">설명</span><span class="sxs-lookup"><span data-stu-id="19b30-123">Remarks</span></span>

<span data-ttu-id="19b30-124">이 샘플 애플리케이션에서는 실행할 테스트를 지정하는 명령줄 매개 변수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-124">The sample application accepts command line parameters indicating which test you would like to execute.</span></span> <span data-ttu-id="19b30-125">노드가 10개인 목록을 SOAP 포맷터를 사용하여 **Test.xml** 파일로 직렬화하려면 **sx Test.xml 10** 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-125">To serialize a 10-node list to a file named **Test.xml** using the SOAP formatter, use the parameters **sx Test.xml 10**.</span></span>

<span data-ttu-id="19b30-126">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-126">For Example:</span></span>

```console
Serialize.exe -sx Test.xml 10
```

<span data-ttu-id="19b30-127">이전 샘플의 **Test.xml** 파일을 deserialize하려면 매개 변수로 **dx Test.xml**을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-127">To deserialize the **Test.xml** file from the previous example, use the parameters **dx Test.xml**.</span></span>

<span data-ttu-id="19b30-128">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-128">For Example:</span></span>

```console
Serialize.exe -dx Test.xml
```

<span data-ttu-id="19b30-129">위의 두 예제에서 명령줄 스위치에 있는 "x"는 XML SOAP serialization을 사용하도록 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-129">In the two examples above, the "x" in the command line switch indicates that you want XML SOAP serialization.</span></span> <span data-ttu-id="19b30-130">이진 serialization을 사용하려면 대신 "b"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-130">You can use "b" in its place to use binary serialization.</span></span> <span data-ttu-id="19b30-131">매우 많은 노드를 serialize하는 경우에는 콘솔 출력을 파일로 리디렉션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-131">If you wish to try serialization with a very large number of nodes, you might want to redirect the console output to a file.</span></span>

<span data-ttu-id="19b30-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-132">For Example:</span></span>

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

<span data-ttu-id="19b30-133">이 샘플에 사용된 클래스 및 기술이 아래에 간략하게 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-133">The following bullets briefly describe the classes and technologies used by this sample.</span></span>

- <span data-ttu-id="19b30-134">런타임 serialization</span><span class="sxs-lookup"><span data-stu-id="19b30-134">Runtime Serialization</span></span>

  - <span data-ttu-id="19b30-135"><xref:System.Runtime.Serialization.IFormatter> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 개체를 참조하기 위해 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-135"><xref:System.Runtime.Serialization.IFormatter> Used to refer to either a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> object.</span></span>

  - <span data-ttu-id="19b30-136">연결된 목록을 스트림에 이진 형식으로 serialize하기 위해 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-136"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Used to serialize a linked list to a stream in a binary format.</span></span> <span data-ttu-id="19b30-137">이진 포맷터는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 형식에서만 인식할 수 있는 형식을 사용하지만,</span><span class="sxs-lookup"><span data-stu-id="19b30-137">The binary formatter uses a format that only the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type understands.</span></span> <span data-ttu-id="19b30-138">데이터가 간결해지는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-138">However, the data is concise.</span></span>

  - <span data-ttu-id="19b30-139"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>은 연결 된 목록을 SOAP 형식의 스트림으로 serialize 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-139"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Used to serialize a linked list to a stream in the SOAP format.</span></span> <span data-ttu-id="19b30-140">SOAP는 표준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-140">SOAP is a standard format.</span></span>

- <span data-ttu-id="19b30-141">스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="19b30-141">Stream I/O</span></span>

  - <span data-ttu-id="19b30-142">serialize 및 deserialize를 위해 <xref:System.IO.Stream>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-142"><xref:System.IO.Stream> Used to serialize and deserialize.</span></span> <span data-ttu-id="19b30-143">이 샘플에서 사용되는 특정 스트림 형식은 <xref:System.IO.FileStream> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-143">The specific stream type used in this sample is the <xref:System.IO.FileStream> type.</span></span> <span data-ttu-id="19b30-144">그러나 serialization에는 <xref:System.IO.Stream>에서 파생되는 모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-144">However, serialization can be used with any type derived from <xref:System.IO.Stream>.</span></span>

  - <span data-ttu-id="19b30-145">디스크에 파일을 생성하고 디스크의 파일을 읽기 위한 <xref:System.IO.File> 개체를 만들기 위해 <xref:System.IO.FileStream>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-145"><xref:System.IO.File> Used to create <xref:System.IO.FileStream> objects for reading and creating files on disk.</span></span>

  - <span data-ttu-id="19b30-146">연결된 목록을 serialize 및 deserialize하기 위해 <xref:System.IO.FileStream>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b30-146"><xref:System.IO.FileStream> Used to serialize and deserialize linked lists.</span></span>

## <a name="see-also"></a><span data-ttu-id="19b30-147">참조</span><span class="sxs-lookup"><span data-stu-id="19b30-147">See also</span></span>

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
- [<span data-ttu-id="19b30-148">기본 serialization</span><span class="sxs-lookup"><span data-stu-id="19b30-148">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="19b30-149">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="19b30-149">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="19b30-150">특성을 사용하여 XML serialization 제어</span><span class="sxs-lookup"><span data-stu-id="19b30-150">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="19b30-151">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="19b30-151">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="19b30-152">serialization</span><span class="sxs-lookup"><span data-stu-id="19b30-152">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="19b30-153">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="19b30-153">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
