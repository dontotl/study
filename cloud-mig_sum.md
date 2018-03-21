# amazon migration

 > azure to aws
   vm export CloudXplorer [URL](http://clumsyleaf.com/products/cloudxplorer)
   vm import AWS VM import [URL](https://aws.amazon.com/ko/ec2/vm-import/)

- VM level migration step 1

  AWS는 다음 유형의 VM import, export를 지원. 이미지를  S3에 업로드 후 활용
  (VMware ESX & Workstation, MS Hyper-V, Citrix Xen)
  (Filetype : OVA, VMDK, VHD, RAW)

- VM level migration step 2

  VM 임포트 후,
  AutoScaling, CloudWatch, Elastic Load Balancing 및 여러 AWS 서비스를 적용 가능

 - VM export with S3 과금 정책
  [URL](https://aws.amazon.com/ko/s3/pricing/)

  예시) 1TB VM export 후 인터넷 전송 비용
       0.023 $ * 1024(스토리지) + 0.08 $ * 1024(네트워크) = 23 $ + 82 $ = 105$ (한화 약 11만원)

  > opc to aws
   아직 opc를 aws로 전환하는 방안은 없고, oracle database를 aws로 이관하거나,
   aws aurora 로 이관하는 전략만 있음
   [URL](https://aws.amazon.com/ko/getting-started/projects/migrate-oracle-to-amazon-aurora/)

   - AWS DB 마이그레이션 도구

     AWS Schema Conversion Tool 로 이기종 DB 스키마 컨버전 지원
     AWS Database Migration Service 로 이기종 DB 데이터 마이그레이션 지원

   - AWS Schema Conversion

    [URL](https://docs.aws.amazon.com/SchemaConversionTool/latest/userguide/Welcome.html)

     지원 DB 목록

     <source>           <target>
     MS SQL SERVER      Amazon Aurora, MS SQL Server, MySQL, PostgreSQL
     MySQL              Amazon Aurora, MySQL, PostgreSQL
     Oracle             Amazon Aurora, MySQL, Oracle, PostgreSQL
     PostgreSQL         Amazon Aurora, MySQL, PostgreSQL

     Greenplum          Amazon Redshift
     MS SQL Server      Amazon Redshift
     Netezza            Amazon Redshift
     Oracle             Amazon Redshift
     Teradata           Amazon Redshift
     Vertica            Amazon Redshift

   - AWS Database Migration Service

     [URL](https://aws.amazon.com/ko/dms/)
     유료 서비스이지만, Aurora, Redshift, DynamoDB 를 타겟으로 전환시 6개월간 무료.   
     별도 VM인프라를 사용하여, VM shape, 스토리지, 데이터 전송비용이 과금됨(동일 AWS가용영역간 전송 무료 )  

# azure migration

  > aws to azure
    vm export using AWS VM export [URL](https://aws.amazon.com/ko/ec2/vm-import/)
    vm import using AZURE vm upload feature [URL](https://docs.microsoft.com/ko-kr/azure/virtual-machines/windows/aws-to-azure)
    [URL](https://docs.microsoft.com/ko-kr/azure/virtual-machines/windows/upload-generalized-managed)

  - VM 임포트 전에,
    스토리지 구성, virtual network 구성, 퍼블릭 IP구성, RDP 및 네트웤 보안 구성, 크리덴셜, NIC및 OS구성의 복잡한 과정을 거친뒤 VM임포트하여 서비스 생성

  - VM 유형은 Citrix PV, AWS PV만 지원  

  > Azure Site Recovery
   [URL](https://docs.microsoft.com/ko-kr/azure/site-recovery/site-recovery-overview)
    on-premise to azure, aws to azure 간 리플리케이션 구성을 활용한 서비스 이관
    on-premise는 baremetal 윈도우, VMware VM, Hyper-V 등을 지원

  > opc to azure, google cloud to azure
    정리된 문서 없음 

# oracle migration

 > OCI marketplace
 - [URL](https://cloudmarketplace.oracle.com/marketplace/oci)

 > migration applications
  Time Machine, Commvault, Cloudify, CloudDat for Oracle Cloud,
  Imanis Data, CoIP Security Enclave, RackWare RMM 6.0 for Bare Metal Cloud,
  ATAsphere, Cost Transparancy

 > migration services
   IBM 컨설팅 서비스가 마켓플레이스에 등재되어 있음.
