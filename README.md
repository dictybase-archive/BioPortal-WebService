# NAME

BioPortal::WebService

# VERSION

version 1.0.0

# NAME

BioPortal::WebService - Perl API for accessing ontologies from NCBO bioportal

# USAGE

First get an apikey from [NCBO BioPortal](http://bioportal.bioontology.org)

## Get an ontology

    use BioPortal::WebService;

    my $portal = BioPortal::WebService->new(api_key => $apikey);
    my $ontology = $portal->get_ontology('GO');
    say $ontology->name;

## Iterate and get individual terms

     my $itr = ontology->get_all_terms;
     while(my $term = $itr->next_term) {
        say sprintf "%s\t%s\t%s", $term->name, $term->definition, $term->identifier;
     }

# INTERFACE

## get\_ontology

- Retrieves an ontology by name,  and returns a [BioPortal::Ontology](http://search.cpan.org/perldoc?BioPortal::Ontology) object

## For rest of the __API__ look at [BioPortal::Base](http://search.cpan.org/perldoc?BioPortal::Base)

# AUTHOR

Siddhartha Basu <biosidd@gmail.com>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2012 by Siddhartha Basu.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.