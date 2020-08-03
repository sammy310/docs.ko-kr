---
title: 프로젝션 형식을 제어하는 방법(C#)
description: C#에서 LINQ의 프로젝션 형식을 제어하여 XElement의 IEnumerable<T>이 아닌 형식 컬렉션을 만드는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
ms.openlocfilehash: 32b019b5e1574e7160b4dce5fb0322caa3c1ca71
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103340"
---
# <a name="how-to-control-the-type-of-a-projection-c"></a>프로젝션 형식을 제어하는 방법(C#)
프로젝션은 데이터 집합을 하나 가져와서 필터링하고 모양을 변경하며 형식까지도 변경하는 프로세스입니다. 대부분의 쿼리 식은 프로젝션을 수행합니다. 이 단원에 나와 있는 대부분의 쿼리 식은 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>로 확인되지만 다른 형식의 컬렉션을 만들기 위해 프로젝션의 형식을 제어할 수 있습니다. 이 항목에서는 프로젝션의 형식을 제어하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 형식 `Customer`를 정의합니다. 쿼리 식은 `Customer` 절에서 새 `Select` 개체를 인스턴스화합니다. 이에 따라 쿼리 식의 형식이 <xref:System.Collections.Generic.IEnumerable%601>의 `Customer`이 됩니다.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
public class Customer  
{  
    private string customerID;  
    public string CustomerID{ get{return customerID;} set{customerID = value;}}  
  
    private string companyName;  
    public string CompanyName{ get{return companyName;} set{companyName = value;}}  
  
    private string contactName;  
    public string ContactName { get{return contactName;} set{contactName = value;}}  
  
    public Customer(string customerID, string companyName, string contactName)  
    {  
        CustomerID = customerID;  
        CompanyName = companyName;  
        ContactName = contactName;  
    }  
  
    public override string ToString()  
    {  
        return $"{this.customerID}:{this.companyName}:{this.contactName}";
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement custOrd = XElement.Load("CustomersOrders.xml");  
        IEnumerable<Customer> custList =  
            from el in custOrd.Element("Customers").Elements("Customer")  
            select new Customer(  
                (string)el.Attribute("CustomerID"),  
                (string)el.Element("CompanyName"),  
                (string)el.Element("ContactName")  
            );  
        foreach (Customer cust in custList)  
            Console.WriteLine(cust);  
    }  
}  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Linq.Enumerable.Select%2A>
