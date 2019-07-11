---
title: '방법: JSON 데이터 직렬화 및 역직렬화'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 0c56b298737dc9b9902f13c586edffb3d05257f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783004"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>방법: JSON 데이터 serialize 및 deserialize
JSON(JavaScript Object Notation)은 클라이언트 브라우저 및 AJAX 사용 웹 서비스 간에 소량의 데이터를 신속하게 교환할 수 있는 효율적인 데이터 인코딩 형식입니다.  
  
 이 문서에는.NET 형식 개체를 JSON 인코딩된 데이터로 serialize 한 다음 다시.NET 형식의 인스턴스를 JSON 형식으로 데이터를 deserialize 하는 방법을 보여 줍니다. 이 예제에서는 데이터 계약을 사용 하 여 사용자 정의의 serialization 및 deserialization을 보여 주기 위해 `Person` 형식을 사용 하 여 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>입니다.  
  
 일반적으로 JSON serialization 및 deserialization은 자동으로 처리 Windows Communication Foundation (WCF)에서 AJAX 사용 끝점을 통해 노출 되는 서비스 작업에서 데이터 계약 형식을 사용 하는 경우. 그러나 경우에 따라 JSON 데이터로 직접 작업 해야 합니다.   
  
> [!NOTE]
>  서버 또는 다른 이유로 보내는 회신의 serialization 동안 오류가 발생 하는 경우 가져오기 반환 수 클라이언트에 오류 라고 합니다.  
  
 이 기사는 기준으로 합니다 [JSON serialization](../samples/json-serialization.md) 샘플입니다.  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a>사용자 형식에 대 한 데이터 계약을 정의 하려면 
  
1. `Person`를 클래스에 연결하고 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 serialize할 멤버에 연결하여 <xref:System.Runtime.Serialization.DataMemberAttribute>에 대한 데이터 계약을 정의합니다. 데이터 계약에 대 한 자세한 내용은 참조 하세요. [서비스 계약 디자인](../designing-service-contracts.md)합니다.  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a>형식 Person의 인스턴스를 JSON으로 serialize하려면  
  
1. `Person` 형식의 인스턴스를 만듭니다.  
  
    ```csharp  
    var p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2. Serialize 된 `Person` 개체를 사용 하 여 메모리 스트림으로 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>합니다.  
  
    ```csharp  
    var stream1 = new MemoryStream();  
    var ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 메서드를 사용하여 JSON 데이터를 스트림에 씁니다.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4. JSON 출력을 표시합니다.  
  
    ```csharp  
    stream1.Position = 0;  
    var sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a>JSON에서 형식 Person의 인스턴스를 deserialize하려면  
  
1. `Person`의 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> 메서드를 사용하여 JSON 인코딩된 데이터를 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>의 새 인스턴스로 deserialize합니다.  
  
    ```csharp  
    stream1.Position = 0;  
    var p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2. 결과를 표시합니다.  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a>예제  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    // Create User object.  
    var user = new User("Bob", 42);  
  
    // Create a stream to serialize the object to.  
    var ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    var ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    var deserializedUser = new User();  
    var ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    var ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  JSON serializer는 다음 샘플 코드에서처럼 동일한 이름의 여러 멤버를 가진 데이터 계약에 대한 serialization 예외를 throw합니다.  
  
```csharp  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}

[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a>참고자료

- [독립 실행형 JSON serialization](stand-alone-json-serialization.md)
- [JSON에 대 한 지원 및 기타 데이터 전송 형식](support-for-json-and-other-data-transfer-formats.md)
