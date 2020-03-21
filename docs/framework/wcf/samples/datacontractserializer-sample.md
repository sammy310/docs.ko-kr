---
title: DataContractSerializer 샘플
ms.date: 03/30/2017
helpviewer_keywords:
- XML Formatter
ms.assetid: e0a2fe89-3534-48c8-aa3c-819862224571
ms.openlocfilehash: 5e1a471cc4cc43b2aa36143eeecc18f7ec17b81a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183785"
---
# <a name="datacontractserializer-sample"></a>DataContractSerializer 샘플
DataContractSerializer 샘플은 데이터 계약 클래스에 대한 일반 serialization 및 deserialization 서비스를 수행하는 <xref:System.Runtime.Serialization.DataContractSerializer>를 보여 줍니다. 샘플은 개체를 `Record` 만들고 메모리 스트림으로 직렬화하고 메모리 스트림을 다른 `Record` 개체로 다시 직렬화하여 <xref:System.Runtime.Serialization.DataContractSerializer>을 사용하여 보여 줍니다. 그런 다음 이진 작성기로 `Record` 개체를 deserialize하여 이진 작성기가 serialization에 미치는 영향을 보여 줍니다.  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 `Record`에 대한 데이터 계약이 다음 샘플 코드에 나와 있습니다.  
  
```csharp  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
internal class Record  
{  
    private double n1;  
    private double n2;  
    private string operation;  
    private double result;  
  
    internal Record(double n1, double n2, string operation, double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    [DataMember]  
    internal double OperandNumberOne  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [DataMember]  
    internal double OperandNumberTwo  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [DataMember]  
    internal string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]  
    internal double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
  
    public override string ToString()  
    {  
        return $"Record: {n1} {operation} {n2} = {result}";
    }  
}  
```  
  
 샘플 코드는 `Record`이라는 `record1` 개체를 만든 다음 해당 개체를 표시합니다.  
  
```csharp
Record record1 = new Record(1, 2, "+", 3);  
Console.WriteLine("Original record: {0}", record1.ToString());  
```  
  
 이 샘플에서는 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 `record1`을 메모리 스트림으로 serialize합니다.  
  
```csharp  
MemoryStream stream1 = new MemoryStream();  
  
//Serialize the Record object to a memory stream using DataContractSerializer.  
DataContractSerializer serializer = new DataContractSerializer(typeof(Record));  
serializer.WriteObject(stream1, record1);  
```  
  
 그런 다음 샘플에서는 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 메모리 스트림을 다시 새 `Record` 개체로 역직렬화하고 표시합니다.  
  
```csharp  
stream1.Position = 0;  
  
//Deserialize the Record object back into a new record object.  
Record record2 = (Record)serializer.ReadObject(stream1);  
  
Console.WriteLine("Deserialized record: {0}", record2.ToString());  
```  
  
 기본적으로 `DataContractSerializer`는 XML의 텍스트 표현을 사용하여 개체를 스트림으로 인코딩합니다. 그러나 다른 작성기를 전달하여 XML의 인코딩에 영향을 줄 수 있습니다. 이 샘플에서는 <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>를 호출하여 이진 작성기를 만듭니다. 그런 다음 <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>를 호출할 때 작성기와 레코드 개체를 serializer에 전달합니다. 마지막으로 작성기를 플러시하고 스트림 길이를 보고합니다.  
  
```csharp  
MemoryStream stream2 = new MemoryStream();  
  
XmlDictionaryWriter binaryDictionaryWriter = XmlDictionaryWriter.CreateBinaryWriter(stream2);  
serializer.WriteObject(binaryDictionaryWriter, record1);  
binaryDictionaryWriter.Flush();  
  
//report the length of the streams  
Console.WriteLine("Text Stream is {0} bytes long", stream1.Length);  
Console.WriteLine("Binary Stream is {0} bytes long", stream2.Length);  
```  
  
 샘플을 실행하면 원래 레코드와 역직렬화된 레코드가 표시된 다음 텍스트 인코딩과 이진 인코딩의 길이를 비교한 내용이 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```console  
Original record: Record: 1 + 2 = 3  
Deserialized record: Record: 1 + 2 = 3  
Text Stream is 233 bytes long  
Binary Stream is 156 bytes long  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.  
  
2. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3. 샘플을 실행하려면 client\bin\client.exe를 입력하여 명령 프롬프트에서 클라이언트를 시작합니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractSerializer`  
