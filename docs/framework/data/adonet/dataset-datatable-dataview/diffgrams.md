---
description: '자세히 알아보기: Diffgram'
title: DiffGram
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: df00bbfb2c25014ff4e73a2777511bd3593ff8a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652512"
---
# <a name="diffgrams"></a>DiffGram

DiffGram은 현재 및 원래의 데이터 요소 버전을 식별하는 XML 형식입니다. <xref:System.Data.DataSet>은 DiffGram 형식을 사용하여 자신의 내용을 로드하고 유지시키며 네트워크 연결을 통한 전송을 위해 이 내용을 serialize합니다. <xref:System.Data.DataSet>이 diffgram으로 작성 되 면 diffgram은 스키마가 아닌 <xref:System.Data.DataSet> **원래** 및 **현재** 행 버전의 열 값, 행 오류 정보 및 행 순서를 포함 하 여의 내용을 정확 하 게 다시 만드는 데 필요한 모든 정보로 채워집니다.  
  
 XML Web services로부터 <xref:System.Data.DataSet>을 보내고 검색할 때 DiffGram 형식이 암시적으로 사용됩니다. 또한 <xref:System.Data.DataSet> **ReadXml** 메서드를 사용 하 여 xml에서의 콘텐츠를 로드 하거나 WriteXml 메서드를 사용 하 여 xml로의 콘텐츠를 작성 하는 경우 <xref:System.Data.DataSet> 내용을 DiffGram으로 읽거나 쓰도록 지정할 수 있습니다.  자세한 내용은 [xml에서 데이터 집합 로드](loading-a-dataset-from-xml.md) 및 [데이터 집합 콘텐츠를 xml 데이터로 작성](writing-dataset-contents-as-xml-data.md)을 참조 하세요.  
  
 DiffGram 형식은 .NET Framework에서 주로 <xref:System.Data.DataSet>의 내용에 대한 serialization 형식으로 사용되지만 DiffGrams을 사용하여 Microsoft SQL Server 데이터베이스의 테이블에 있는 데이터를 수정할 수도 있습니다.  
  
 Diffgram은 모든 테이블의 내용을 요소에 기록 하 여 생성 됩니다 **\<diffgram>** .  
  
### <a name="to-generate-a-diffgram"></a>Diffgram을 생성하려면  
  
1. Root 테이블(부모가 없는 테이블) 목록을 생성합니다.  
  
2. 목록의 각 테이블 및 해당 하위 항목에 대해 첫 번째 Diffgram 섹션에 모든 행의 현재 버전을 기록합니다.  
  
3. 의 각 테이블에 대해 <xref:System.Data.DataSet> Diffgram의 섹션에 모든 행의 원래 버전 (있는 경우)을 작성 합니다 **\<before>** .  
  
4. 오류가 있는 행의 경우 Diffgram의 섹션에 오류 내용을 기록 합니다 **\<errors>** .  
  
 Diffgram은 XML 파일의 시작부터 끝의 순서로 처리됩니다.  
  
### <a name="to-process-a-diffgram"></a>Diffgram을 처리하려면  
  
1. 행의 현재 버전이 포함된 Diffgram의 첫 번째 섹션을 처리합니다.  
  
2. **\<before>** 수정 및 삭제 된 행의 원래 행 버전이 포함 된 두 번째 또는 섹션을 처리 합니다.  
  
    > [!NOTE]
    > 행이 삭제된 것으로 표시된 경우 현재 `Cascade`의 <xref:System.Data.DataSet> 속성에 따라 삭제 작업에서 행의 하위 항목도 삭제할 수 있습니다.  
  
3. 섹션을 처리 **\<errors>** 합니다. 이 섹션에서 각 항목에 대한 지정된 행과 열의 오류 정보를 설정합니다.  
  
> [!NOTE]
> <xref:System.Data.XmlWriteMode>를 Diffgram로 설정하면 대상 <xref:System.Data.DataSet>과 원래 <xref:System.Data.DataSet>의 내용이 다를 수 있습니다.  
  
## <a name="diffgram-format"></a>DiffGram 형식  

 DiffGram 형식에는 다음 예제에서와 같이 현재 데이터, 원래(또는 "이전") 데이터 및 오류 섹션 등 세 가지 섹션이 있습니다.  
  
```xml  
<?xml version="1.0"?>  
<diffgr:diffgram
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 DiffGram 형식은 다음 데이터 블록으로 구성됩니다.  
  
 **\<**  **_DataInstance_*_  _*>**  
 이 요소의 이름 ***Datainstance** _는이 설명서의 설명을 위해 사용 됩니다. _*_Datainstance_*_ 요소는 <xref:System.Data.DataSet> 의 또는 행을 나타냅니다 <xref:System.Data.DataTable> . _DataInstance * 대신 요소는 또는의 이름을 포함 합니다 <xref:System.Data.DataSet> <xref:System.Data.DataTable> . 이 DiffGram 형식의 블록에는 수정 여부에 관계없이 현재 데이터가 들어 있습니다. 수정 된 요소 또는 행은 **diffgr: hasChanges** 주석으로 식별 됩니다.  
  
 **\<diffgr:before>**  
 이 DiffGram 블록 형식에는 행의 원래 버전이 포함됩니다. 이 블록의 요소는 _ *diffgr: id** 주석을 사용 하는 ***datainstance** _ 블록의 요소와 일치 합니다.  
  
 **\<diffgr:errors>**  
 이 DiffGram 블록 형식에는 ***Datainstance** _ 블록의 특정 행에 대 한 오류 정보가 포함 되어 있습니다. 이 블록의 요소는 _ *diffgr: id** 주석을 사용 하 여 _*_datainstance_*_ 블록의 요소와 일치 합니다.  
  
## <a name="diffgram-annotations"></a>DiffGram 주석  

 DiffGrams은 여러 주석을 사용하여 <xref:System.Data.DataSet>에서 다른 행 버전이나 오류 정보를 표시하는 다양한 DiffGrams 블록의 요소를 나타냅니다.  
  
 다음 표에서는 DiffGram 네임 스페이스 **urn: 스키마-microsoft-com: xml-DiffGram-v1** 에 정의 된 diffgram 주석에 대해 설명 합니다.  
  
|Annotation|Description|  
|----------------|-----------------|  
|**id**|의 요소와 블록의 요소를 쌍으로 연결 하는 데 사용 **\<diffgr:before>** **\<diffgr:errors>** **\<** **_DataInstance_*_ _*>** 됩니다. **Diffgr: id** 주석이 있는 값은 *[TableName] [RowIdentifier]* 형식입니다. `<Customers diffgr:id="Customers1">`를 예로 들 수 있습니다.|  
|**parentId**|**\<** **_DataInstance_*_ _*>** 현재 요소의 부모 요소인 블록의 요소를 식별 합니다. **Diffgr: parentId** 주석이 있는 값은 *[TableName] [RowIdentifier]* 형식입니다. `<Orders diffgr:parentId="Customers1">`를 예로 들 수 있습니다.|  
|**hasChanges**|블록의 행을 **\<** **_DataInstance_*_ _*>** 수정 된 것으로 식별 합니다. **Haschanges** 주석에는 다음 두 값 중 하나를 사용할 수 있습니다.<br /><br /> **장착**<br /> **추가** 된 행을 식별 합니다.<br /><br /> **수정됨**<br /> 블록의 **원래** 행 버전이 포함 된 **수정** 된 행을 식별 **\<diffgr:before>** 합니다. **삭제** 된 행은 블록에 **원래** 행 버전이 **\<diffgr:before>** 있지만 블록에는 주석이 추가 된 요소가 없습니다 **\<** **_DataInstance_*_ _*>** .|  
|**hasErrors**|RowError를 사용 하 여 블록의 행을 식별 **\<** **_DataInstance_*_ _*>** 합니다.  Error 요소는 블록에 배치 됩니다 **\<diffgr:errors>** .|  
|**오류**|블록의 특정 요소에 대 한 **RowError** 의 텍스트를 포함 **\<diffgr:errors>** 합니다.|  
  
 <xref:System.Data.DataSet>에는 자신의 내용을 DiffGram으로 읽거나 작성할 때 추가 주석이 포함됩니다. 다음 표에서는 **urn: msdata** 의 네임 스페이스에 정의 된 이러한 추가 주석을 설명 합니다.  
  
|Annotation|설명|  
|----------------|-----------------|  
|**RowOrder**|원래 데이터의 행 순서를 유지하며 특정 <xref:System.Data.DataTable>에 있는 행의 인덱스를 식별합니다.|  
|**숨김**|**ColumnMapping** 속성이 **mappingtype.attribute** 로 설정 된 열을 식별 합니다. 특성은 **msdata: hidden** *[ColumnName]*= "*value*" 형식으로 작성 됩니다. `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`를 예로 들 수 있습니다.<br /><br /> 데이터가 있는 숨겨진 열만 DiffGram 특성으로 작성됩니다. 그렇지 않으면 무시됩니다.|  
  
## <a name="sample-diffgram"></a>샘플 DiffGram  

 다음은 DiffGram 형식의 예제입니다. 이 예제에서는 변경 사항이 커밋되기 전에 테이블에 있는 행을 업데이트한 결과를 보여 줍니다. CustomerID가 "ALFKI"인 행이 수정되었지만 업데이트되지는 않았습니다. 결과적으로 블록에 **diffgr: id** 가 "Customers1" 인 **현재** 행 **\<** **_DataInstance_*_ _*>** 과 블록에 **Diffgr: Id** 가 "Customers1" 인 **원래** 행이 있습니다 **\<diffgr:before>** . CustomerID가 "ANATR" 인 행에는 **RowError** 가 포함 되므로로 주석이 추가 되 `diffgr:hasErrors="true"` 고 블록에는 관련 요소가 있습니다 **\<diffgr:errors>** .  
  
```xml  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## <a name="see-also"></a>참조

- [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)
- [XML에서 데이터 세트 로드](loading-a-dataset-from-xml.md)
- [데이터 세트 콘텐츠를 XML 데이터로 작성](writing-dataset-contents-as-xml-data.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
