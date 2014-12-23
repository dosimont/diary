# IPTW14 Review - Found Issues and questions

## Main page

- [X] provided wrong e-mail: 'first.last@imag.fr'?!

## Intro 
- [ ] Better resoliution for Fig. 1 _Regenerate using SET 1.0_

## Section 3

### Subsection 3.1

- [ ] 3rd paragraph (p.5) is unclear: How are data partitioned, based on time, hardware resources, similarity of metric values?
- [ ] p.6 enumeration of partitioning steps: step 3: what would be not allowed partitions?

### Subsection 3.2

- [X] 2nd paragraph: first appearance of acronym "pIC", should be followed directly by acronym explanation (parametrized Information Criterion) - not several lines later in the formula.
- [X] p.6 between Eq. (2) and Eq. (3) 'and a defines ...' -> 'and define a ...'
- [X] Fig. 2-6: color legend missing

### Subsection 3.5.1

- [ ] Add a bit info how the aggregation is done - first time than space or both at same time.

### Subsection 3.5.2

- [X] before Eq.1 superflous white space: '... followed :' --> '... followed:'
- [ ] A bit info about the selection of aggregation sets could be added, because it is clear, that the number of possible aggregations is binomially high.

## Section 4

## Subsection 4.1.1

- [X] 2nd paragraph (p.13): 'The Figure 7 ...' --> 'A screenshot of the GUI is shown in Figure 7.'
- [ ] Better resolution for Fig. 7 

## Subsection 4.1.2

- [X] pipeline Step. 6/7: Add ref. to Fig.7 as it makes this point clearer
- [X] pipeline Step. 8: Are the partitions asscociated to the different p values stored or recomputed?

## Subsection 4.1.3

- [ ] example Fig for the mentioned Gantt chart-like diagram?

## Subsection 4.2

- [X] is it small 'o' or big 'O'; for LaTeX setting see http://texblog.org/2014/06/24/big-o-and-related-notations-in-latex/
- [X] Is it correct, that the visualisation is left over to Eclipse/Java which makes it as slow as 10 sec in the worst case? Could it be improved by using C++/GTK/Qt,...?
_Indeed, performances depends partially on Eclipse and SWT/Draw2D, and would probably be better with OpenGL, for instance_
- [X] Note: Fig.8-10 not mentioned in text
_They are, page 15_
- [X] Fig.8:
  a) shows no difference in execution time for different timeslice numbers at the lower event number part. Why?
_Our microscopic model building is parallel, which provokes is a slight overhead : each thread get a fixed number of events and then process them to compute the values to put in the microscopic model. Some synchronizations are necessary, which can lead the thread to wait for the access to the ressouces. For very small traces, one thread is often sufficient to do the complete job, since it gets all the events of the trace in once. This prevents synchronization, which explains why the influence of time slices is not visible_
  b) does the execution time includes reading the trace? (maybe answer to question a)
- [X] Fig.9: This suggests, that the temporal aggregation is the most time consuming part? But looking at table 1 this is not the case. _In Fig 9 the x axis represents |T|²*|S|*|U| and not the trace size: indeed, this step complexity only depends on the microscopic size. The microscopic models we use for our analyses correspond to the beginning of the x axis (ex: a microscopic model with |T|=100, |S|=1000 and |U|=100 gives |T|²*|S|*|U|=10^9. This is the classic order of magnitude we use in our use cases)_
- [X] Fig.8-10: How connect these data together - were the same trace data used for all Fig.8-10?
_No: for Fig 9-10, we generate artifical microscopic models with random values. Our objective is to show the algorithm complexity. We thus use very huge microscopic models. In real use cases (table 1), times are a lot lower since microscopic models are smaller_
- [X] p.17: Typo: 'can be deal ...' --> 'can be dealt ...'
- [ ] 4.2: Was the trace stored on the SSD? more detailed SSD specifications would be interesting SATA-2 or SATA-3, read speed.
