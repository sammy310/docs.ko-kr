---
title: NetDataContractSerializer의 기능을 공급하기 위해 DataContractSerializer 및 DataContractResolver를 사용
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: e7a4f0d754b444d8558b03e07d98788a2eee5971
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144984"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="a0333-102">NetDataContractSerializer의 기능을 공급하기 위해 DataContractSerializer 및 DataContractResolver를 사용</span><span class="sxs-lookup"><span data-stu-id="a0333-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="a0333-103">이 샘플에서는 <xref:System.Runtime.Serialization.DataContractSerializer>와 적절한 <xref:System.Runtime.Serialization.DataContractResolver>를 함께 사용하여 <xref:System.Runtime.Serialization.NetDataContractSerializer>와 동일한 기능을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="a0333-104">이를 위해 적절한 <xref:System.Runtime.Serialization.DataContractResolver>를 만드는 방법과 이를 <xref:System.Runtime.Serialization.DataContractSerializer>에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

## <a name="sample-details"></a><span data-ttu-id="a0333-105">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="a0333-105">Sample details</span></span>
 <span data-ttu-id="a0333-106"><xref:System.Runtime.Serialization.NetDataContractSerializer>는 serialize된 XML에 CLR 형식 정보를 포함하지만 <xref:System.Runtime.Serialization.DataContractSerializer>는 그렇지 않으며 이는 <xref:System.Runtime.Serialization.NetDataContractSerializer>와 <xref:System.Runtime.Serialization.DataContractSerializer>의 중요한 차이점 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="a0333-107">따라서 직렬화하는 쪽과 역직렬화하는 쪽이 모두 동일한 CLR 형식을 공유하는 경우에만 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="a0333-108">그러나 <xref:System.Runtime.Serialization.DataContractSerializer>는 <xref:System.Runtime.Serialization.NetDataContractSerializer>보다 성능이 우수하므로 이를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="a0333-109"><xref:System.Runtime.Serialization.DataContractSerializer>에서는 <xref:System.Runtime.Serialization.DataContractResolver>를 추가하여 serialize되는 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>

 <span data-ttu-id="a0333-110">이 샘플은 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-110">This sample consists of two projects.</span></span> <span data-ttu-id="a0333-111">첫 번째 프로젝트에서는 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용하여 개체를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="a0333-112">두 번째 프로젝트에서는 <xref:System.Runtime.Serialization.DataContractSerializer>와 <xref:System.Runtime.Serialization.DataContractResolver>를 함께 사용하여 첫 번째 프로젝트와 동일한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>

 <span data-ttu-id="a0333-113">다음 코드 예제에서는 DCSwithDCR 프로젝트의 <xref:System.Runtime.Serialization.DataContractResolver>에 추가된 `MyDataContractResolver`라는 사용자 지정 <xref:System.Runtime.Serialization.DataContractSerializer>의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        type ??= Type.GetType(typeName + ", " + typeNamespace);
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="a0333-114">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a0333-114">To use this sample</span></span>

1. <span data-ttu-id="a0333-115">Visual Studio 2012를 사용하여 DCRSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-115">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="a0333-116">솔루션 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-116">Right-click the solution file and choose **Properties**.</span></span>

3. <span data-ttu-id="a0333-117">솔루션 **속성 페이지** 대화 상자에서 **공통 속성**, **시작 프로젝트**에서 여러 시작 프로젝트를 선택합니다. **Multiple startup projects:**</span><span class="sxs-lookup"><span data-stu-id="a0333-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>

4. <span data-ttu-id="a0333-118">**DCSwithDCR** 프로젝트 옆에서 **작업** 드롭다운에서 **시작을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>

5. <span data-ttu-id="a0333-119">**NetDCS** 프로젝트 옆에서 **작업** 드롭다운에서 **시작을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>

6. <span data-ttu-id="a0333-120">**확인**을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-120">Click **OK** to close the dialog.</span></span>

7. <span data-ttu-id="a0333-121">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-121">To build the solution, press CTRL+SHIFT+B.</span></span>

8. <span data-ttu-id="a0333-122">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-122">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0333-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a0333-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a0333-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a0333-125">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a0333-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0333-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
