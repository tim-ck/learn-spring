# learn-spring
where i place notes and project

## JPA Spring
1. create custom JpaRepository. JpaRepository is from spring framwork
``` java
   @NoRepositoryBean
    public interface GenericRepository <T, ID extends   Serializable> 
    	extends JpaRepository<T, ID> {
    	
    	
    	//Method for QBE
    	public List<T> queryByCriteria(Object example);
    	
    	public List<T> queryByCriteria(Object criteria, String optionalFragment);
        
    	public List<T> queryByCriteria(Object criteria, String optionalFragment, int begin, int max, QBECriterionHandler criterionHandler);
    	
        public T uniqueResultByCriteria(Object example);
        
        public T firstResultByCriteria(Object example);
        
        
        
        public T saveWithoutFlush(T entity);
      
        public List<T> saveWithoutFlush(Iterable<? extends T> entities);
        
        public List<T> doQueryWithFilter( String filterName, String filterQueryName, Map inFilterParams, Map inParams );
        
        public List queryNatively(String nativeQueryName, LinkedHashMap<String,Class<?>> inEntityClasses, Map inParams );
        
        public void refresh(T obj);
        
        public T merge(T obj);
        
        @Deprecated
        public void persist(T obj); 
        
        public void detach(T obj );
        @Deprecated
        public T update(T obj );
        
        public void delete(ID id);
        
        public void delete(Iterable<? extends T> entities);
    
        
        public   T findOne(ID id) ;
        
          public <S extends T> List<S> save(Iterable<S> entities) ;
      }
```

  2.Create Entity
``` java
    @Entity
    @Table(name="MTRK_LOCATION")
    public class MtrkLocation implements Serializable {
    	private static final long serialVersionUID = 1L;
    
    	@Id
    	@Column(name="CODE")
    	private String code;
    
    	@Column(name="ENG_DESC")
    	private String engDesc;
    	
    	@Column(name="Location_Group")
    	private String locationGroup;

    //getter setter
```
